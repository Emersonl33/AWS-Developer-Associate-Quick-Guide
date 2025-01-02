<p align= "center">
  <img src="./Icons/Arch_Amazon-Virtual-Private-Cloud_64%405x.png" alt="VPC-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
VPC
    </h1>
</p>

VPC (Virtual Private Cloud) é um dos pilares fundamentais de uma cloud pública, e o serviço de redes da AWS. Ele oferece um ambiente seguro e isolado para executar suas instâncias de Amazon EC2, bancos de dados, containers e outros recursos. É essencial para quem precisa de controle total sobre o tráfego de rede e a arquitetura de rede na nuvem. As VPCs são regionais e gratuitas. 

## Sub-redes (Subnets)
- Você pode dividir sua VPC em várias sub-redes (subnets), que são segmentos menores da rede. Cada sub-rede pode ser configurada para ser pública (acessível da internet) ou privada (isolada da internet).

## VPN e Conectividade Híbrida
- É possível conectar sua VPC a uma rede local (on-premises) via VPN (Virtual Private Network) ou através de uma AWS Direct Connect para estabelecer uma conexão privada de alta performance entre sua infraestrutura local e a nuvem da AWS.

## Peering de VPC
- Você pode peering (fazer a conexão) entre duas ou mais VPCs para permitir que elas se comuniquem de maneira segura sem conexão pela internet públca. Isso é útil, por exemplo, para compartilhar recursos entre ambientes de diferentes contas da AWS.
- VPC Peering não é transitivo: Ou seja, se você tem a VPC A conectada à VPC B, e a VPC B conectada à VPC C, isso não significa que a VPC A pode se comunicar com a VPC C automaticamente. Se quiser que a VPC A se comunique com a VPC C, você precisa configurar o peering entre essas duas VPCs também. Para conexões transitivas, use o Transit Gateway.

## Internet Gateway (IGW)
- Permite que recursos dentro da VPC se comuniquem com a internet.

## NAT Gateway/Instance
- Permite que instâncias em sub-redes privadas acessem a internet sem expô-las diretamente à internet. Útil para bancos de dados em sub-redes privadas que precisam acessar a internet para baixar patches e atualizações.

## VPC Endpoint:
-  Permite que instâncias privadas se comuniquem com serviços da AWS, como S3 ou DynamoDB, sem precisar sair da VPC e sem acessar a internet.

| Tipo de Endpoint       | Serviços Suportados                | Descrição                                                     |
|------------------------|------------------------------------|---------------------------------------------------------------|
| **Interface Endpoint**  | Qualquer serviço que suporta AWS PrivateLink (ex: S3, DynamoDB, EC2) | Conecta a serviços da AWS ou terceiros através de ENIs privadas. |
| **Gateway Endpoint**    | Amazon S3 e DynamoDB               | Conecta a serviços específicos (S3 e DynamoDB) através de tabelas de roteamento sem sair da rede privada. |


## Transit Gateway
- Um ponto central de conexão entre VPCs e conexões on-premise (VPN ou Direct Connect). O Transit Gateway oferece controle centralizado de roteamento. Você pode definir rotas que determinam como o tráfego será direcionado entre as VPCs, redes locais e outras conexões de rede, sem a necessidade de configurar manualmente tabelas de roteamento complexas.

## Security Groups e ACLs

| Característica               | **Network ACLs**                             | **Security Groups**                           |
|------------------------------|----------------------------------------------|-----------------------------------------------|
| **Nível de Aplicação**       | Sub-rede (afetando toda a sub-rede)          | Instância (afeta instâncias específicas)      |
| **Tipo de Regras**           | Permite regras de **permitir** e **negar**    | Apenas regras de **permitir**                 |
| **Estado**                   | **Sem estado** (precisa definir regras de entrada e saída separadamente) | **Com estado** (uma regra de entrada permite também a saída correspondente) |
| **Aplicação de Regras**      | Processamento de regras **sequencial**       | Regras são avaliadas **simultaneamente**      |
| **Direção do Tráfego**       | Aplica-se tanto a **entrada** quanto a **saída** | Controla o tráfego **de entrada** (e saída por padrão) |
| **Uso Comum**                | Controle de tráfego entre **sub-redes**      | Controle de tráfego em **instâncias específicas** |
| **Padrão**                   | **Permitir** todo o tráfego por padrão       | **Negar** todo o tráfego de entrada por padrão |

## :books: Referências
 - *https://docs.aws.amazon.com/vpc/*
<br />
<br />