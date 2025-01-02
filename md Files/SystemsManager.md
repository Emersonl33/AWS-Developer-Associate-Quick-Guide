<p align= "center">
  <img src="./Icons/Arch_AWS-Systems-Manager_64%405x.png" alt="SystemsManager-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Systems Manager
    </h1>
</p>

O AWS Systems Manager é como um controle remoto para sua infraestrutura na AWS. Sabe quando você tem um monte de coisas para fazer e quer automatizar ou controlar tudo sem ter que ir em cada máquina ou servidor manualmente? É isso que o Systems Manager faz: ele ajuda a gerenciar e automatizar tudo de forma centralizada e prática. <br>
Se você está gerenciando várias instâncias EC2 e precisa garantir que todas estejam com os patches de segurança mais recentes, você pode usar o Patch Manager para aplicar os patches automaticamente. 

## Recursos
- Automation: O recurso Automation permite a automação de tarefas de manutenção e operacionais de forma fácil e sem necessidade de scripts complexos. Ele ajuda a criar fluxos de trabalho automatizados para ações como implantação de patches, atualizações de segurança, restauração de backups, entre outros. É possível utilizar runbooks (livros de execução) pré-configurados ou criar fluxos de trabalho personalizados.
- O Run Command permite executar comandos em instâncias EC2 e servidores on-premises, de forma remota e sem precisar acessar cada servidor manualmente
- O Session Manager oferece uma maneira segura de acessar instâncias EC2 e servidores sem a necessidade de abrir portas SSH ou RDP. Ele cria sessões de terminal interativo, permitindo a administração remota de instâncias de forma segura e sem a necessidade de credenciais, apenas usando IAM (Identity and Access Management).
- O Parameter Store oferece um local seguro para armazenar dados sensíveis como chaves de API, strings de conexão de banco de dados, e outros segredos. Ele permite que você armazene valores de parâmetros em texto simples ou criptografado e acesse-os de forma programática, integrando-os com outras ferramentas ou scripts.
- O State Manager ajuda a garantir que suas instâncias EC2 ou servidores locais mantenham um estado desejado de configuração. Ele pode ser usado para aplicar configurações, como instalação de software ou configuração de parâmetros, e para monitorar se o sistema está conforme o esperado. Caso algo seja alterado, o State Manager pode corrigir automaticamente.
- Patch Manager: Manter todos os servidores atualizados é muito importante, certo? O Patch Manager automatiza as atualizações de segurança em todas as suas máquinas, para garantir que nada fique vulnerável.
- O Maintenance Windows ajuda a agendar e gerenciar as janelas de manutenção de sistemas e recursos, como patches ou atualizações, garantindo que essas atividades aconteçam em horários planejados e não impactem os usuários ou a operação crítica.
- O Systems Manager Insights é um recurso mais novo que permite monitorar e diagnosticar instâncias EC2 em tempo real, coletando métricas e logs para detectar possíveis problemas ou oportunidades de melhoria.

## SSM Parameter Store
**Esse tópico merece uma atenção especial!!! O exame vai testar sua clareza da diferença entre esse recurso e outros que fazem administração de chaves**
- Não tem rotação de chaves nativa
- Útil para parâmetros simples (strings) e segredos (criptografados).
- Parâmetros podem ser armazenados como **SecureString**, que são criptografados com AWS KMS (Key Management Service).
- Útil para armazenamento de parâmetros de configuração não críticos.
- Armazenamento de segredos sensíveis, mas sem a complexidade da rotação automática.
- O custo é mais baixo quando comparado ao Secrets Manager para uso simples de armazenamento de segredos.

| **Característica**                 | **SSM Parameter Store**                     | **AWS KMS**                          | **Secrets Manager**                       |
|------------------------------------|---------------------------------------------|--------------------------------------|-------------------------------------------|
| **Objetivo**                       | Armazenamento de parâmetros e segredos.     | Gerenciamento de chaves de criptografia. | Armazenamento e rotação de segredos.     |
| **Tipo de dados**                  | Parâmetros simples e secretos.             | Chaves criptográficas.               | Segredos (ex: senhas, chaves de API).     |
| **Criptografia**                   | Usando KMS para `SecureString`.             | Criptografia de chaves.              | Criptografia usando KMS.                 |
| **Rotação automática**             | Não nativa (requere Lambda).                | Não se aplica (gera chaves, não segredos). | Suporte nativo para rotação automática.  |
| **Versionamento**                  | Sim, suporta versionamento de parâmetros.   | Não se aplica.                       | Sim, suporta versionamento de segredos.  |
| **Gerenciamento de chaves**        | Não gerencia chaves de criptografia.        | Gerencia apenas chaves de criptografia. | Não se aplica.                           |
| **Casos de uso principais**        | Armazenamento de parâmetros e segredos simples. | Criptografar dados em outros serviços. | Gerenciar segredos sensíveis e rotação de credenciais. |
| **Custo**                          | Mais barato para uso simples.              | Custos por operação de chave.        | Mais caro, mas oferece funcionalidade avançada. |

## :books: Referências
 - *https://docs.aws.amazon.com/pt_br/systems-manager/latest/userguide/application-manager.html*
<br />
<br />
