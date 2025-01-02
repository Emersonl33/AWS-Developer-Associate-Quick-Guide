<p align= "center">
  <img src="./Icons/Arch_Amazon-EC2_64%405x.png" alt="EC2-icon" style="height:180px; width:180px;"/>
<br />
    <h2 align="center">
EC2
    </h2>
</p>

O Amazon EC2 (Elastic Compute Cloud) é o principal serviço da AWS, com ele você pode subir instâncias de servidores virtuais na nuvem para executar aplicativos e serviços de forma escalável e flexível.

## Tipos de instâncias
- General Purpose: Instâncias balanceadas para uma ampla variedade de aplicações (ex: t3, m5).
- Compute Optimized: Para cargas de trabalho que exigem maior poder de processamento (ex: c5).
- Memory Optimized: Para aplicações que exigem grandes quantidades de memória (ex: r5, x1e).
- Storage Optimized: Para cargas de trabalho com grandes necessidades de armazenamento local de alta performance (ex: i3, d2).
- Accelerated Computing: Instâncias com GPUs ou FPGAs para tarefas de machine learning, gráficos ou computação científica (ex: p3, inf1).

## Integração com ELB
- O EC2 pode ser usado junto com o Elastic Load Balancer para distribuir o tráfego de entrada entre as instâncias EC2, garantindo balanceamento de carga e alta disponibilidade.

## IP Privado 
- Fixo dentro da VPC, não acessível pela internet, utilizado para comunicação interna entre instâncias.

## IP Público
- Dinâmico, atribuído a instâncias EC2, acessível pela internet, mas muda ao reiniciar a instância.

## Elastic IPs
- Os IPs elásticos (EIP) são IPs públicos permanentes e podem ser associados ou dissociados de instâncias EC2 conforme necessário. IPs elásticos precisam ser contratados e são pagos. 

## Security Groups
- Toda vez que você sobe uma EC2, essa instãncia precisa ser associada a um SG (Security Group), se ela não for associada a um SG existente será criado um automaticamente.
- SGs são statefull, ou seja, você só precisa configurar tráfego de entrada. Para os CIDRs com tráfego de entrada permitido, o tráfego de saída é automaticamente configurado como permitido também.

## Key Pairs
- No momento da configuração de uma EC2 é possível atribuir key pairs a elas. O EC2 utiliza pares de chaves (Key Pairs) para autenticação SSH, permitindo acesso seguro a instâncias Linux/Unix ou RDP para instâncias Windows.

## Instance Metadata 
- Permite que as instâncias EC2 acessem informações sobre elas mesmas, como ID, tipo, e zona de disponibilidade, para automação e configuração.
- Exemplo: Uma instância EC2 pode acessar sua própria instance metadata via HTTP em http://169.254.169.254/latest/meta-data/ para obter o seu ID da instância.

## Formas de acesso
- SSH (Para Linux): A instância deve estar com porta 22 aberta no Security Group e a chave privada (arquivo .pem) deve estar disponível. Comando exemplo pra acesso SSH: ssh -i /caminho/para/chave.pem ec2-user@<IP_Público>
- RDP (para Windows):  Você usa o **Remote Desktop Client** para se conectar, usando um usuário e senha obtidos da instância.
- Session Manager (para gerenciar instâncias sem chaves SSH ou RDP):Funciona com instâncias EC2 registradas no AWS Systems Manager. Permite a execução de comandos diretamente na instância a partir do console AWS ou AWS CLI. A instância deve ter a IAM Role adequada e o SSM Agent deve estar instalado e funcionando. No Console da AWS, vá em Systems Manager > Session Manager e selecione a instância para iniciar uma sessão interativa.
- EC2 Instance Connect (conexão via navegador para instâncias Linux):  Conexão SSH diretamente via navegador para instâncias Linux, sem necessidade de chave privada. Usando o EC2 Instance Connect diretamente no console da AWS, você pode se conectar à instância usando o navegador. No Console AWS, vá em EC2 > Instances > Connect > EC2 Instance Connect e clique em Connect.
- Bastion Host: Para acessar instâncias privadas por meio de uma instância Host intermediária
- AWS VPN: Acesso seguro à VPC por meio de um tunelamento privado.
- Elastic IP Para garantir que você tenha um IP público fixo, o Elastic IP pode ser associado à sua instância, permitindo o acesso consistente via SSH ou RDP, mesmo após reinicializações. Após associar o Elastic IP à instância, use SSH ou RDP como faria com um IP público normal.

## Tipos de contratação

| **Opção de Compra**       | **Descrição**                                                                                                                                 | **Quando Usar**                                                                                                                                                        | **Vantagens**                                                                                                                                                                                                                                                                                  |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Instâncias sob Demanda** | Paga-se pela capacidade de computação com base no uso, sem necessidade de compromissos.                                                          | Ideal para cargas de trabalho imprevisíveis ou de curto prazo, onde a demanda de recursos não pode ser prevista.                                                     | - Pagamento por hora ou por segundo.<br>- Flexibilidade para iniciar ou parar instâncias a qualquer momento.<br>- Sem compromisso de longo prazo.                                                                                                                                                        |
| **Instâncias Reservadas**  | Capacidades reservadas por 1 ou 3 anos, com descontos significativos em comparação às instâncias sob demanda.                                   | Ideal para cargas de trabalho com demanda previsível e constante ao longo do tempo.                                                                                   | - Desconto de até 75% em relação às instâncias sob demanda.<br>- Opções de pagamento: pagamento total, parcial ou nada no momento da compra.<br>- Garantia de capacidade na região escolhida.                                                                                                                |
| **Instâncias Spot**        | Utiliza a capacidade ociosa do EC2 com grandes descontos. O preço varia conforme a oferta e demanda.                                            | Ideal para cargas de trabalho flexíveis e tolerantes a falhas, como processamento em lote ou renderização de gráficos.                                                | - Descontos de até 90% em relação às instâncias sob demanda.<br>- Pagamento conforme a tarifa do mercado.<br>- Flexibilidade de ser interrompido, se necessário.                                                                                                                                      |
| **EC2 Savings Plans**      | Compromisso de uso por 1 ou 3 anos em troca de descontos. Oferece flexibilidade para mudar instâncias, regiões e sistemas operacionais.          | Ideal para quem busca descontos com flexibilidade para diferentes tipos de instâncias e regiões.                                                                    | - Desconto de até 72% em relação às instâncias sob demanda.<br>- Flexibilidade para mudar tipos de instâncias, regiões e sistemas operacionais.<br>- Compromisso de uso por 1 ou 3 anos com diferentes opções de pagamento.                                                                              |
| **Instâncias Dedicadas**   | Instâncias EC2 em hardware dedicado, sem compartilhamento com outras contas AWS.                                                              | Ideal para cargas de trabalho que exigem conformidade com regulamentos específicos ou isolamento físico por questões de segurança.                                     | - Garantia de que a infraestrutura não é compartilhada com outras contas AWS.<br>- Pagamento por hora.<br>- Combinação possível com instâncias sob demanda ou reservadas.                                                                                                                         |

## Tipos de armazenamento para instâncias
| **Tipo de Armazenamento**            | **Descrição**                                                                                             | **Quando Usar**                                                                                                                   | **Vantagens**                                                                                                         |
|--------------------------------------|-----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Amazon EBS (Elastic Block Store)** | É o tipo de armazenamento default para instâncias EC2. Oferece discos rígidos virtuais com alta performance.| Ideal para aplicações que necessitam de armazenamento persistente e de alto desempenho, como bancos de dados e sistemas de arquivos.| - Armazenamento persistente, mesmo após a parada da instância.<br>- Opções de desempenho otimizadas para diferentes necessidades.<br>- Suporte a snapshots para backup e recuperação.|
| **Instâncias com Armazenamento Local (Instance Store)** | Armazenamento temporário associado à instância EC2. O armazenamento é apagado quando a instância é parada.     | Ideal para dados temporários, caches e buffers onde a persistência não é necessária.                                             | - Alta performance devido ao armazenamento local.<br>- Ideal para armazenamento temporário e de baixo custo.            |
| **Amazon EFS (Elastic File System)** | Sistema de arquivos totalmente gerenciado para ser usado por múltiplas instâncias EC2 simultaneamente.      | Ideal para aplicativos que necessitam de um sistema de arquivos compartilhado acessado por múltiplas instâncias EC2.             | - Armazenamento escalável e compartilhado.<br>- Acesso simultâneo de várias instâncias.<br>- Backup automático.       |
| **Amazon FSx**                       | Oferece sistemas de arquivos gerenciados, como o Windows File Server ou Lustre, para necessidades específicas de armazenamento. | Ideal para cargas de trabalho que exigem sistemas de arquivos de alto desempenho, como aplicações HPC ou aplicações com alta necessidade de IOPS. | - Sistemas de arquivos gerenciados e de alta performance.<br>- Suporte a aplicações empresariais e de alto desempenho.<br>- Fácil integração com Active Directory para autenticação. |

## AMI
Uma AMI (Amazon Machine Image) é basicamente uma "imagem" ou "modelo" que contém tudo o que você precisa para rodar um servidor na AWS, como o sistema operacional, programas e configurações. É como uma receita para criar uma instância EC2 (que é o servidor virtual), permitindo que você crie várias instâncias com a mesma configuração de forma rápida e fácil. Você pode criar sua própria AMI a partir de uma instância já configurada ou usar uma imagem pronta fornecida pela AWS.

- **AMIs de Mercado:** Se você estiver usando uma AMI do AWS Marketplace, ela pode ter um custo adicional. Essas AMIs geralmente incluem software licenciado que a AWS cobra, como sistemas operacionais comerciais (Windows, por exemplo) ou outras soluções de software específicas.

## ASG (Auto Scaling Group)
O Auto Scaling group é um utilizado para aumentar ou diminuir o número de instâncias em execução com base em métricas de desempenho.

### Principais features do ASG:
- O ASG é regional, ou seja, ele só roda dentro de uma Region, onde vc pode distribuir suas máquinas, ao longo das zonas de disponibilidade.
- Ajuste de capacidade com base em políticas: Permite configurar políticas para aumentar ou diminuir o número de instâncias com base em métricas de desempenho ou horários específicos.
- Se não houver nenhuma política de terminação de instâncias configurada, o comportamento padrão é que o ASG termine a instância mais antiga
- Verificação de integridade: Substitui automaticamente instâncias que falham ou se tornam inoperantes.
- Tamanho mínimo, desejado e máximo: Define o número mínimo, desejado e máximo de instâncias a serem mantidas pelo grupo.
- Escalonamento programado: Permite configurar o escalonamento de instâncias em horários específicos, por exemplo, para aumentar a capacidade em horários de pico.
- Ações de saúde das instâncias: Monitoramento contínuo da saúde das instâncias, removendo e substituindo automaticamente aquelas que falham nos testes de integridade.
- Integração com Elastic Load Balancer (ELB): O ASG pode ser integrado com um ELB para distribuir automaticamente o tráfego entre as instâncias saudáveis.
- Notificações de escalonamento: Permite configurar notificações quando eventos de escalonamento ocorrem, como a adição ou remoção de instâncias.
- Capacidade de escalonamento vertical: Permite aumentar ou diminuir a capacidade de instâncias EC2 no grupo (como a alteração do tipo de instância).
- Suporte a instâncias spot: Pode incluir instâncias spot no grupo de Auto Scaling, aproveitando os preços mais baixos das instâncias não reservadas.

## :books: Referências
 - *https://aws.amazon.com/pt/ec2/?trk=ca05c99e-6c1c-48b2-a660-7554e13f56fc&sc_channel=ps&s_kwcid=AL!4422!10!71880800487097!71881323169036&ef_id=438f66dd4d9216f2fec501acd579c9cf:G:s&msclkid=438f66dd4d9216f2fec501acd579c9cf*
<br />
<br />