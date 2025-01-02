<p align= "center">
  <img src="./Icons/Arch_AWS-CodeDeploy_64%405x.png" alt="CodeDeploy-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CodeDeploy
    </h1>
</p>

O CodeDeploy é um serviço de entrega contínua (Continuous Delivery - CD), facilita a automação do processo de deploy (implantação) do seu código em qualquer lugar: seja em servidores EC2, instâncias On-Premises ou em containers. Ele cuida de transferir sua aplicação de um repositório (como GitHub ou S3) para o ambiente de produção sem que você precise fazer tudo manualmente, garantindo que o processo de deploy seja repetível, confiável e sem falhas. <br/ >
Tipo o seu assistente para garantir que o código certo vai para o lugar certo, sem stress, com rollback automático se algo der errado! 😎

## Plataformas suportadas
- Instâncias EC2 
- Servidores locais (on-premises), (***Atenção pra esse ponto!***) usando o CodeDeploy Agent.
- Contêineres no Amazon ECS (Elastic Container Service).
- Lambda (com suporte para deploy de funções Lambda).

## Tipos de Deploy
| Tipo de Deploy            | Descrição                                                                 | Vantagens                                                                                     | Desvantagens                                                                               |
|---------------------------|---------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| **Rolling Deploy**         | A implantação é feita de forma gradual, atualizando uma parte das instâncias de cada vez. | - Menos impacto em produção, com atualizações graduais. <br> - Redução de riscos.              | - Processo mais demorado. <br> - Mistura de versões antigas e novas nas instâncias.        |
| **Blue/Green Deploy**      | Duas versões do sistema são mantidas: uma em produção (blue) e outra com a nova versão (green). O tráfego é redirecionado para a versão nova quando ela estiver pronta. | - Zero downtime.<br> - Rollback fácil (voltar para a versão anterior).                          | - Maior custo (duas versões precisam ser mantidas). <br> - Maior uso de recursos.            |
| **Canary Deploy**          | O novo código é implantado inicialmente em um pequeno número de instâncias ou usuários e gradualmente expandido. | - Menor risco e exposição. <br> - Detecção precoce de problemas.                               | - Implantação mais lenta. <br> - Complexidade no gerenciamento de tráfego.                 |
| **All-at-Once Deploy**     | O código é implantado em todas as instâncias simultaneamente.             | - Rápido e simples.<br> - Ideal para sistemas pequenos ou não críticos.                       | - Downtime (interrupção no serviço). <br> - Maior risco de falhas afetarem todo o sistema.   |
| **Feature Toggles**        | Funcionalidades novas são implantadas, mas desativadas, e podem ser ativadas dinamicamente sem nova implantação. | - Lançamento controlado de novos recursos. <br> - Facilita testes A/B.                        | - Aumento na complexidade do código. <br> - Risco de "toggles" não removidos no futuro.     |
| **Shadow Deploy**          | A nova versão é implantada, mas sem tráfego real, apenas para teste e monitoramento. | - Testa o novo código com tráfego real sem afetar os usuários. <br> - Identificação de problemas de desempenho. | - Custo mais alto, pois envolve tráfego duplicado. <br> - Não é uma implantação "real".    |
| **A/B Testing Deploy**     | Duas versões do sistema são implantadas e o tráfego é dividido entre elas para comparar o desempenho. | - Permite comparar o desempenho de versões diferentes. <br> - Ideal para experimentos controlados. | - Requer divisão de tráfego. <br> - Mais complexo para gerenciar.                          |

## Estrutura de Arquivos
- Arquivo appspec.yml: Este é o arquivo principal de configuração do CodeDeploy, que define como a implantação deve ser realizada, incluindo as etapas do processo e as localizações dos arquivos.
- O arquivo appspec.yml deve estar localizado na raiz do pacote de artefatos de implantação.
- A pasta scripts/ contém os scripts que são executados durante as diferentes fases da implantação. Esses scripts são referenciados no arquivo appspec.yml na seção hooks.

```shell
<root>/
│
├── appspec.yml          # Arquivo de configuração do CodeDeploy
├── scripts/             # Pasta contendo scripts executáveis para cada fase da implantação
│   ├── before_install/  # Scripts a serem executados antes da instalação
│   ├── install/         # Scripts a serem executados durante a instalação
│   ├── after_install/   # Scripts a serem executados após a instalação
│   ├── application_start/  # Scripts para iniciar o aplicativo
│   └── application_stop/   # Scripts para parar o aplicativo
│
├── <outros arquivos de código>  # O código e arquivos a serem implantados
│
└── <outros diretórios ou arquivos adicionais>  # Arquivos necessários pela aplicação

```
## Hooks
- Os hooks do CodeDeploy são como "gatilhos" que executam comandos ou scripts em momentos específicos do processo de deploy, ele define oq deve ser feito como: antes de começar, depois que terminou ou se algo deu errado. Eles ajudam a personalizar o processo de deploy e garantir que tudo funcione do jeito que você precisa.
- O CodeDeploy executa os hooks na ordem em que são definidos no appspec.yml, e um hook deve ser executado completamente antes que o próximo inicie. Se algum hook falhar, o processo de implantação será interrompido
- BeforeInstall: Usar Quando você precisar fazer preparações iniciais, como verificar a saúde do sistema, desinstalar versões anteriores ou instalar dependências.
- Install:  Usar Para tarefas relacionadas ao processo de instalação real dos artefatos de aplicação.
- AfterInstall: Usar para tarefas de pós-instalação, como ajustes de permissões de arquivos ou configuração adicional.
- ApplicationStart: Usar Para iniciar o serviço ou aplicação implantada após a instalação e configuração.
- ApplicationStop: Para parar serviços ou processos antes de implantar uma nova versão.
- ValidateService: Para realizar testes pós-implantação para garantir que a aplicação foi implantada com sucesso e está funcionando como esperado. Serve para Testar a saúde da aplicação e verificar endpoints HTTP ou outras verificações de status.

```yaml
version: 0.0
os: linux

files:
  - source: /src
    destination: /var/www/html
  - source: /config/settings.conf
    destination: /etc/myapp/settings.conf

hooks:
  BeforeInstall:
    - location: scripts/before_install/stop_old_service.sh
      timeout: 90
      runas: root

  Install:
    - location: scripts/install/deploy_files.sh
      timeout: 120
      runas: root

  AfterInstall:
    - location: scripts/after_install/set_permissions.sh
      timeout: 60
      runas: root

  ApplicationStart:
    - location: scripts/application_start/start_new_service.sh
      timeout: 180
      runas: root

  ApplicationStop:
    - location: scripts/application_stop/stop_new_service.sh
      timeout: 60
      runas: root

  ValidateService:
    - location: scripts/validate_service/test_service.sh
      timeout: 120
      runas: root

```
## :books: Referências
 - *https://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html*
<br />
<br />