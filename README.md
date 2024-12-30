# AWS Certified Developer Associate - Study Guide 📚☁️

Esse repositório é um compilado com os pontos mais importantes de todo conteúdo que consumi durante minha preparação para a certificação **AWS Developer Associate**.
<br>
A idéia é trazer um guia de estudos com conceitos fundamentais sobre o que é cobrado no exame.
- **O repositório está organizado por tópicos e serviços relevantes para a certificação, todo conteúdo está contido nesse README e também pode ser acessado pelos arquivos .md**

## Sobre o Exame 🎯

A certificação **AWS Certified Developer Associate** tem como objetivo validar seus conhecimentos sobre ferramentas de desenvolvimento dentro da AWS. Para essa certificação é recomendado que você tenha pelo menos 1 ano de exeperiência com desenvolvimento na AWS. 
Isso pode ser adquirido por meio de cursos, labs práticos disponíveis no skillbuilder https://aws.amazon.com/pt/training/digital/ ou projetos profissionais e pessoais livres. Abuse do Free Tier para experimentar os recursos. <br>
- O exame tem 65 questões de múltipla escolha e mútipla alternativa(com 2 selecões ou 3 selecões) as questões de múltipla escolha têm 4 alternativas e as de múltipla alternativa têm 5 ou 6 alternativas.
- A pontuacao é contabilizada numa escala de 100-1000, sendo considerado aprovado quem tem pontuacão >= 720. Essa pontuacão não representa percentual de acerto, existem questões que valem mais que outras e algumas tem pontuacão zerada por serem de caráter experimental e 
  estatístico. Dentro da minha experiência com simulados oficiais, o menor número de acertos que fiz pra atingir 720 pontos foram 37 questões aka 57% de acerto, lembrando que acertar esse número de questões não é garantia de aprovacão, um número seguro seria acima de 45 questões.
- A duracao do exame é de 130 Minutos. Você pode ter 30 minutos acrescidos se optar por fazer em inglês e for um não nativo do idioma.
- Preco: $150 USD. Com frequência a AWS distribui vouchers de 33-50% de desconto pra certificacoes de nível associate. Além de 50% de desconto pra quem conseguiu certificar a Cloud Practitioner. 
- O exame é dividido por área de conhecimento e cada área de conhecimento tem um peso:
  
| **Domínio**                     | **Peso** | **Principais Serviços**                                                                                   |
|----------------------------------|-----------------|----------------------------------------------------------------------------------------------------------|
| Desenvolvimento                 | 32%             | AWS EC2, AWS Lambda, API Gateway, AWS SDK, AWS CLI, AWS CDK, AWS SAM, DynamoDB, AWS RDS, AWS Aurora, ElastiCache, AWS S3, AWS EFS, AWS EBS, CloudFront, Route 53, Step Functions, AWS SNS, AWS SQS, Amazon Kinesis, AWS AppSync, AWS Athena, AWS OpenSearch Service|
| Segurança                       | 26%             | AWS IAM, AWS STS, AWS Cognito, Certificate Manager (ACM), AWS KMS, AWS Secrets Manager, AWS WAF, AWS VPC|
| Deployment                      | 24%             | AWS Elastic Beanstalk, AWS CodePipeline, AWS CodeBuild, AWS CodeDeploy, AWS CodeCommit, AWS CloudFormation, AWS CodeGuru, Amazon ECS/EKS/ECR/Fargate, AWS Amplify               |
| Otimização e Solução de Problemas | 18%             | Amazon CloudWatch, AWS Cloud Trail, AWS X-Ray, AWS Trusted Advisor, AWS EventBridge, Elastic Load Balancind (ELB), Auto Scaling Group (ASG),                                          |

<br>
Para mais detalhes: https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS-Certified-Developer-Associate_Exam-Guide.pdf

# Conteúdo do Exame 📚🌐
Nessa secão vou organizar o conteúdo do exame de acordo com o tipo do serviço.

Alguns grupos de serviços são considerados essenciais para compreensão do funcionamento básico de uma topologia cloud, é boa ideia comećar por aqui:
- Identidade e Segurança
- Computação
- Armazenamento
- Redes
- Bancos de dados
- Observabilidade e Auditoria

O foco princiapl fica por conta das ferramentas de desenvolvimento, e é aqui que está a carga de complexidade desse exame, A AWS vai fazer muitas perguntas relacionadas ao funcionamento detalhado desses serviços e como resolver problemas utilizando eles:
- Deploy
- Development Tools
- App integration
- Data Ingestion and Analytics
- Containers

- [Lambda](Lambda.md) 🔧
- [ECS](ECS.md) 🐋
- [EKS](EKS.md) 🛞

### 🖥️ ****Desenvolvimento (32%)****

- [API Gateway](API-Gateway.md) 🌐
- [Elastic Beanstalk](Elastic-Beanstalk.md) 🌱
- [CodeArtifact](CodeArtifact.md) 📦
- [CodeBuild](CodeBuild.md) ⚙️
- [CodeDeploy](CodeDeploy.md) 🚀
- [CodeCommit](CodeCommit.md) 💼
- [CodePipeline](CodePipeline.md) 🔄
- [CodeStar](CodeStar.md) ⭐
- [CloudFormation](CloudFormation.md) 🏗️
- [SAM (Serverless Application Model)](SAM.md) 🐿️
- [SDK (Software Development Kit)](SDK.md) 🔧
- [CDK (Cloud Development Kit)](CDK.md) ☁️
- [X-Ray](X-Ray.md) 🔍

### 💾 **Armazenamento**

- [S3](S3.md) 🗂️
- [EBS](EBS.md) 🗂️
- [EFS](EFS.md) 🗂️

### 🏗️ **Infra Estrutura**

- [Elastic Load Balancer (ELB)](ELB.md) ⚖️
 
### 🌐 **Rede**

- [Route 53](Route53.md) 🌍
- [VPC](VPC.md) 🖧
- [CloudFront](CloudFront.md) ⚡
- [Global Acelerator](GlobalAcelerator.md) 📡

### 🔍 **Monitoramento**

- [CloudWatch](CloudWatch.md) ⏰
- [CloudTrail](CloudTrail.md) 📑
  
### 🚀 **Desenvolvimento de Aplicações e Integração com AWS**

- [SQS](SQS.md) 📦
- [SNS](SNS.md) 📢
- [Kinesis](Kinesis.md) 🔄

### 🎲 **Banco de Dados**

- [DynamoDB](DynamoDB.md) 📊
- [Aurora](Aurora.md) 🌌
- [RDS](RDS.md) 🗄️

### ⚡ **Eventos e Integração**

- [EventBridge](EventBridge.md) 🌩️

<br/ >

<h1 align= "center"> 
  Segurança e Identidade🔒 
</h1>
<p align= "center">
  <img src="./Icons/Arch_AWS-Identity-and-Access-Management_64%405x.png" alt="IAM-icon" style="height:180px; width:180px;"/>
<br />
    <h2 align="center">
IAM
    </h2>
</p>
<br />

O IAM (Identity Access Management) é o gerenciador de permissões e acessos da AWS. O IAM é um serviço gratuito e global.
Com ele é possível criar usuários, grupos, definir políticas de permissões e criar roles.
<br>
<br>
### Usuários, Grupos, Políticas, Roles
- Cada conta AWS é, na verdade, um usuário ###root.
- Um usuário do IAM, é um user criado por uma conta root que vem por default sem nenhum acesso permitido, portanto, sem poder acessar nenhum recurso ou serviço da AWS.
- Um grupo IAM pode conter vários usuários IAM. **Um grupo do IAM NÃO pode conter outro grupo IAM**.
- Uma policy(política, traduzido) é um conjunto de permissões escritas em formato JSON. Cada grupo IAM ou usuário IAM podem possuir de 0 a N policies. Quando você adiciona um usuário IAM a um grupo, você automaticamente associa todas as policies e as permissões anexadas ao grupo a este usuário.
- Roles são permissões temporárias sem a necessidade de compartilhamento de credenciais atribuídas a um serviço (ou usuário) para acessar recursos em outro serviço. Além disso, uma conta pode assumir uma role em outra conta para obter as permissões necessárias para acessar os recursos dessa conta.


### Políticas Gerenciadas pela AWS, Políticas de confiança, Políticas baseadas em recurso
- **Políticas gerenciadas** são criadas e mantidas pela AWS (ou pelo usuário) para ser aplicada a múltiplos usuários, grupos ou roles, como a política AmazonS3ReadOnlyAccess que concede permissões de leitura em todos os buckets S3.

```JSON
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::*",
        "arn:aws:s3:::*/*"
      ]
    }
  ]
}
```
<br />

- **Trust policies** (ou "políticas de confiança") na AWS são um tipo de política associada a uma role (função) que define quem pode assumir essa role. Elas determinam quais entidades (usuários, serviços ou contas) têm permissão para "assumir" a role e agir com as permissões atribuídas a ela. <br>

```JSON
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "ec2.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
<br />

- **Política Baseada em Recursos** são aplicadas diretamente a um recurso da AWS (como um bucket S3 ou uma fila SQS) para controlar quem pode acessar esse recurso, como uma política de bucket S3 que permite que um usuário de outra conta acesse seus objetos.
<br>

```JSON
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::123456789012:user/ExampleUser"
      },
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::example-bucket/*"
    }
  ]
}
```
<br />

### Boas Práticas
- Somente use a conta root para fazer as configurações base na AWS.
- Um usuário físico = Um usuário IAM
- Pratique o princípio de menor privilégio(least privilege principle) dando aos usuários apenas as permissões que eles precisam.
- Adicione Usuários a grupos e Adicione permissões a grupos.
- Crie políticas de senhas fortes.
- Use e Endosse o uso de MFA
- Crie e use Roles para dar permissões para serviços AWS
- Use chaves de acesso(Veja chaves privada/chaves públicas) para acessar CLIs e SDKs
- Faça auditoria nas permissões da conta AWS com o relatório de credenciais IAM.

### STS

**AWS STS** é uma sigla para *Security Token Service* ele permite que se obtenha credenciais temporárias para acessar recursos da AWS diretamente e decodificar mensagens de erro.

- **AssumeRole:** Permite que uma identidade (usuário, serviço, ou conta) assuma uma role e obtenha permissões temporárias.
- **AssumeRoleWIthSAML:**  Retorna credenciais para usuários logados com SAML
- **AssumeRoleWithWebIdentity:** Retorna funções(*roles*) para usuários logados com um IdP (Facebook, Google, e etc) entretanto não utilize mais essa API e sim Cognito Identity Pools
- **GetSessionToken:** Para usuários com MFA ou uma conta *root* da AWS
- **GetFederationToken:** Para obter credenciais temporárias para um *federated user*
- **GetCallerIdentity:** Para retornar detalhes sobre o usuário IAM e a sua função(*role*) usada na chamada da API
- **DecodeAuthorizationMessage:** Para descriptografar mensagens de erro quando uma API da AWS é negada

## :books: Referências
- *https://docs.aws.amazon.com/pt_br/IAM/latest/UserGuide/introduction.html*

<br>
<br>

<p align= "center">
  <img src="/Icons/Arch_Amazon-Cognito_64%405x.png" alt="COGNITO-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
COGNITO
    </h1>
</p>
<br />

O Cognito é um serviço de autenticação e gereciamento de usuários para aplicações mobile e web. Ele permite criar, autenticar e gerenciar usuários, além de fornecer funcionalidades como login social (Facebook, Google, Amazon) e login empresarial (Active Directory, SAML), sem a necessidade de desenvolver um sistema de autenticação no backend. 

### Cognito User Pools
O Cognito User Pool é um diretório permite autenticar e gerenciar **Usuários** 

- Autenticação de usuários: Permite criar e gerenciar usuários para sua aplicação, oferecendo funcionalidades como registro, login, redefinição de senha e verificação de e-mail.
- Login social e federado: Suporte para autenticação via provedores de identidade externa, como Google, Facebook, Amazon, e até provedores corporativos via SAML.
- MFA (Autenticação Multifatorial): Protege o login dos usuários, exigindo mais de uma verificação para garantir maior segurança.
- Customização: Oferece personalização de fluxos de autenticação, como validação de campos, formulários de cadastro e mensagens de erro.
  
### Cognito Identity Pools
O Cognito Identity Pool permite fornecer acesso temporário a recursos da AWS (como S3, DynamoDB, etc.) para usuários autenticados, mesmo que esses usuários não estejam registrados no User Pool. Ele oferece:

- Autenticação federada: Permite que usuários de diferentes fontes de autenticação (como User Pools, provedores de login social, ou até usuários anônimos) obtenham credenciais da AWS.
- Acesso a recursos AWS: Usando o serviço AWS STS (Security Token Service), o Cognito Identity Pool fornece credenciais temporárias para acessar recursos da AWS de forma segura.
- Suporte a usuários anônimos: Permite a interação de usuários não autenticados com os serviços da AWS, mantendo uma camada de segurança e controle de acesso.

### Diferença principal entre User Pools e Identity Pools:
- User Pools são voltados para o gerenciamento de autenticação e dados dos usuários
- Enquanto Identity Pools são usados para fornecer credenciais temporárias de acesso aos recursos da AWS para usuários autenticados ou anônimos.

## :books: Referências
- *https://docs.aws.amazon.com/pt_br/cognitoidentity/latest/APIReference/Welcome.html*
<br />
<br />


<p align= "center">
  <img src="./Icons/Arch_AWS-Key-Management-Service_64%405x.png" alt="KMS-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
KMS
    </h1>
</p>

O AWS Key Management Service (KMS) é um serviço gerenciado de criptografia em repouso que facilita a criação, o gerenciamento, controle e rotação das chaves de criptografia em aplicações e serviços da AWS. 

## CMK
- Customer Master Keys (CMKs): CMKs são chaves mestras que você cria, controla e usa para criptografar e descriptografar dados. Elas podem ser:
- Gerenciadas pelo cliente: Criadas e controladas pelo usuário, com flexibilidade para definir políticas de acesso, rotação, e exclusão.
- Gerenciadas pela AWS: Criadas automaticamente para uso em serviços AWS, como S3 ou EBS.
- Provenientes de HSM: Criadas usando um AWS CloudHSM, garantindo maior controle e conformidade.
- A CMK nunca sai do KMS.
- Ela é usada para criptografar e descriptografar Data Keys, garantindo segurança no processo.

## Data Key
Imagina que você tem uma caixa super importante que quer manter segura. Essa caixa é tão grande que não dá pra ficar levando ela toda hora pro cofre principal (o KMS). Aí o que você faz? Pede ao KMS uma chave temporária só pra cuidar da sua caixa.
O KMS responde assim:
- "Aqui está uma cópia da chave em texto plano pra você usar agora e trancar sua caixa."
- "E aqui está outra cópia da chave, só que criptografada, pra guardar com a caixa caso precise destrancar no futuro."
Essa chave temporária é a Data Key. Ela é:
- Simples e eficiente: Tranca e destranca sua caixa rapidamente.
- Protegida pelo KMS: Se alguém encontrar a cópia criptografada, não consegue usá-la sem passar pelo KMS.
- No fundo, a Data Key é tipo uma chave de "uso diário", enquanto o KMS é o cofre que mantém a segurança de longo prazo. 😉
- Você pode gerar uma Data Key usando a operação ***GenerateDataKey*** do AWS KMS.
- O processo de usar uma Data Key para criptografar dados e protegê-la com uma KMS Key é chamado de Envelope Encryption

## Operações de cripografia
- *Encrypt*: Usa uma CMK para criptografar dados fornecidos pelo cliente.
- *Decrypt*: Descriptografa dados que foram protegidos com uma CMK.
- *GenerateDataKey*: Gera uma Data Key em plainText e uma versão criptografada. Ideal quando você precisa usar a chave imediatamente.
- *GenerateDataKeyWithoutPlaintext*: Retorna apenas a versão criptografada da Data Key, sem nunca expor a chave em um texto plano. Útil para cenários onde a geração e o uso da chave são separados e exige seguranca reforçada.
- *ReEncrypt*: Recriptografa dados que já foram criptografados, trocando a CMK usada.

## Criptografia Simétrica
- Chaves suportadas: Chaves simétricas (AES-256).
- Mesma chave usada para criptografar e descriptografar os dados.
- Ideal para a maioria dos casos de uso no AWS, como proteção de dados em volumes do EBS, objetos no S3 ou bancos de dados no RDS.

## Criptografia por Envelope
- Usa Data Keys (geradas pelo KMS) para criptografar os dados localmente.
- As Data Keys são protegidas por uma CMK simétrica ou assimétrica no KMS.
- Reduz a latência, pois os dados são criptografados localmente com a Data Key.

## Casos de uso das chaves do *GenerateDataKey* e *GenerateDataKeyWithoutPlaintext*
Use GenerateDataKey:
- Quando você precisa criptografar dados imediatamente e deseja simplicidade no fluxo de trabalho.
- Exemplo: Criptografar arquivos ou objetos no momento em que são gerados.
<br>
Use GenerateDataKeyWithoutPlaintext:
- Quando você quer gerar e armazenar chaves para uso posterior, sem risco de exposição.
- Exemplo: Configurar backups seguros onde as chaves criptografadas serão usadas mais tarde.

## Casos de uso Comuns do KMS
- Criptografia em repouso de volumes do EBS, objetos no S3, e bancos de dados usando padrão AES-256 com CMKs simétricas
- Geração de assinaturas digitais com chaves RSA ou ECDSA.
- Gerenciamento e rotação de chaves de criptografia

## Limitações
- Limite de solicitações: Varia de acordo com a região, mas geralmente é de 5.000 a 30.000 solicitações por segundo.
- Para criptografia simétrica (com uma CMK), o tamanho máximo de dados que podem ser criptografados em uma única operação é de 4 KB.
- As CMKs podem ser excluídas, mas você precisa aguardar entre 7 e 30 dias após a solicitação de exclusão para que a chave seja apagada permanentemente.
- O KMS é um serviço regional, o que significa que suas chaves estão disponíveis apenas dentro de uma região da AWS. Caso haja um problema com uma região, as chaves podem não estar acessíveis.
- Você não pode replicar suas chaves entre regiões automaticamente; precisaria criar e gerenciar chaves separadas em cada região.

## :books: Referências
 - *https://docs.aws.amazon.com/kms/*
<br />
<br />

<p align= "center">
  <img src="./Icons/Arch_AWS-WAF_64%405x.png" alt="WAF-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
WAF
    </h1>
</p>

O WAF (Web Application Firewall) é uma camada de segurança que protege aplicações web contra diversos tipos de ataques e ameaças. Ele age em camada 7 (aplicação) monitora, filtra e analisa o tráfego HTTP/HTTPS que entra em um aplicativo web para garantir que ataques maliciosos (como SQL Injection, Cross-Site Scripting (XSS), e ataques de negação de serviço (DDoS)) não cheguem até o servidor ou banco de dados.

## Integrações
- Amazon CloudFront: Usado para proteger sites ou aplicativos com alta carga de tráfego distribuído globalmente. Filtra o tráfego malicioso perto do ponto de origem (bordas da rede), garantindo desempenho um pouco mais rápido que em outras integrações.
- Application Load Balancer (ALB): Protege o tráfego HTTP/HTTPS filtrando requisições antes de chegar aos servidores backend
- API Gateway: Protege APIs públicas contra ataques como injeções SQL e XSS. Ideal para ambientes que expõem microserviços ou APIs RESTful para a internet.

## :books: Referências
 - *https://docs.aws.amazon.com/waf/*
<br />
<br />


<h1 align= "center"> 
  🖥️ Computação
</h1>
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

<p align= "center">
  <img src="./Icons/Arch_AWS-Lambda_64%405x.png" alt="Lambda-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Lambda λ
    </h1>
</p>

**Esse serviço é com certeza o mais cobrado no exame, por isso merece atenção especial e um estudo mais aprofundado.**
O AWS Lambda é um serviço de computação serverless, ou seja, que permite executar código sem *gerenciar servidores*, executando funções em resposta a eventos como uploads de arquivos, modificações em bancos de dados ou requisições HTTP.
O Lambda suporta várias linguagens de programação, como Python, Node.js, Java, C#, Go, Ruby, entre outras...
Você paga pelo tempo de execução do código e pela quantidade de recursos computacionais (memória) que ele utiliza

## Estrutura
- Função Lambda: O código executável.
- Evento: A origem do acionamento da função (ex: um arquivo S3).
- Handler: O método que é executado (***Atenção pra esse ponto!***) Sempre que você for acessar bancos de dados usando lambda se atente para deixar as Strings de autenticação do banco **FORA** do método handler! Isso vai aumentar a performance do seu acesso e execução da função
- Configuração: Tempo limite (***Atenção pra esse ponto!***) As funções lambda têm um tempo de execução máximo de 15 minutos, sendo assim, o uso do Lambda não é adequado para cargas de trabalho que ultrapassem esse tempo.
- Configuração: Memória e CPU (***Atenção pra esse ponto!***) O poder de processamento da CPU do Lambda está diretamente ligado à memória. Quando voê aumenta sua capacidade de memória, sua CPU é automaticamente redimensionada proporcionalmente à quantidade de memória que você aumentou.
- Contexto: Informações sobre a execução.
- IAM Role: Permissões necessárias para acessar outros recursos.

## Invocação Síncrona: 
- O cliente espera pela resposta da função Lambda. O AWS Lambda processa a requisição e retorna o resultado imediatamente para o cliente após a execução da função.
- Usado para invocações em que você precisa da resposta imediatamente, como em APIs ou chamadas diretas de uma aplicação.
- InvocationType='RequestResponse'

## Invocação Assíncrona:
- Na invocação assíncrona, o cliente envia uma requisição para a função Lambda, mas não espera pela resposta. O AWS Lambda coloca o evento em uma fila e a função é invocada assim que possível. O Lambda não retorna a resposta ao cliente.
- Podem ser usados para processamento de arquivos após o upload para o S3 ou processamento de eventos do SNS, por exemplo.
- A execução da função não é limitada a 15 minutos, mas eventos não processados ficam na fila por até 7 dias.
- InvocationType='Event'

## Camadas
- Camadas (Layers) São uma maneira de empacotar e compartilhar código, bibliotecas e dependências que podem ser reutilizados em várias funções Lambda. Em vez de empacotar todas as dependências dentro do código da função, você pode usar camadas para compartilhar essas dependências entre diferentes funções.
- Cada função Lambda pode usar até 5 camadas por vez, incluindo a camada padrão (o código da própria função Lambda)
- O tamanho máximo de uma camada é 50 MB quando compactada. No entanto, é possível usar até 250 MB de dados descompactados.
- Você pode criar camadas e compartilhá-las com outras contas AWS ou regiões.
- Além das bibliotecas de código, você também pode usar camadas para fornecer arquivos específicos do sistema operacional ou scripts de configuração necessários para sua função.

## Versões
- Uma versão de função Lambda é um snapshot imutável do código e da configuração de uma função no momento em que ela é criada
- Uma vez publicada, a versão não pode ser alterada
- Cada versão tem um número único
- Você pode referenciar diretamente uma versão específica de uma função, usando o número da versão (ex.: *arn:aws:lambda:region:account-id:function:function-name:1*).
- Versão $LATEST (***Atenção pra esse ponto!***): O $LATEST é a versão não publicada e em constante atualização. Ele sempre aponta para a versão mais recente do código da função Lambda, mas não é imutável como outras versões publicadas. 
A versão $LATEST não deve ser utilizada em ambientes de produção.

## Aliases
- Um alias é uma referência estável a uma **versão** de uma função Lambda. Enquanto a versão é imutável, o alias permite que você apontar para diferentes versões de uma função.
- Um alias tem um nome estável, como prod, dev, test, etc., e pode apontar para qualquer versão específica de uma função Lambda.
- Um alias não pode apontar para outro alias. (***Atenção pra esse ponto!***)
- Você pode alterar o alias para apontar para diferentes versões, sem alterar o código da função.
- Atribuição de Percentual de Tráfego(***Atenção pra esse ponto!***): Você pode configurar aliases para distribuir o tráfego entre diferentes versões de forma gradual (usado, por exemplo, para deploys canary).

## Exemplo prático
- Suponha que você tenha uma função Lambda com o código em sua versão 1. Se você fizer alterações no código e publicar uma nova versão (versão 2), a versão 1 será preservada e não será afetada.
- Você pode criar um alias chamado prod que aponte para a versão 1 da função. Quando você publicar a versão 2, pode alterar o alias prod para apontar para a nova versão. Assim, o ambiente de produção será atualizado sem afetar outras funções ou versões.

## Execução agendada
- Lambda pode ser invocado em horários específicos ou com base em uma agenda usando Amazon CloudWatch Events.

## Diretório /tmp
- (***Atenção pra esse ponto!***) O diretório /tmp pode ser usado como Cache temporário para cálculos ou estados de execução.
- Capacidade de armazenamento de 512 MB pode ser um limitador para funções que precisam manipular grandes quantidades de dados.
- Como o conteúdo do diretório /tmp é removido após a execução, ele não é adequado para persistir dados entre diferentes invocações de funções Lambda.
- 
## Lambda em contêiners
- Desde 2020, o Lambda permite que você empacote suas funções em containers Docker e execute-os no ambiente Lambda. Isso significa que você não precisa se preocupar com a infraestrutura do contêiner, apenas com o código dentro do contêiner.
- ideal para funções de curta duração. Se sua aplicação pode ser dividida em tarefas discretas e pequenas (por exemplo, processar uploads de arquivos, responder a requisições HTTP em APIs, ou processar eventos de fila), o Lambda pode ser uma solução muito eficaz.

## Execução no ambiente VPC
- Sempre que você precisar acessar recursos que estão limitadas a uma VPC ou sub rede privada, é necessário colocar sua função Lambda dentro dessa VPC
## :books: Referências
 - *https://docs.aws.amazon.com/lambda/*
<br />
<br />

<p align= "center">
  <img src="./Icons/Arch_AWS-Elastic-Beanstalk_64%405x.png" alt="ElasticBeanStalk-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Elastic BeanStalk
    </h1>
</p>

Esse com certeza é mais um tópico super importante para o Exame, e um dos meus serviços favoritos da AWS. <br>
O AWS Elastic Beanstalk é uma maneira fácil de subir e gerenciar aplicações na nuvem sem precisar se preocupar com a infraestrutura. Em vez de configurar servidores, redes e bancos de dados manualmente, você só precisa focar no seu código, e o Beanstalk cuida do resto. <br>
**Imagine o seguinte:** <br>
Você tem uma aplicação web, tipo um site ou uma API, e quer rodá-la na nuvem. Em vez de gastar tempo configurando servidores e instalando coisas, você só faz o upload do código e diz para o Elastic Beanstalk em que linguagem ele foi feito (Python, Java, Node.js, Ruby, etc). Ele automaticamente configura o ambiente para você, escala a aplicação conforme a necessidade e até monitora o desempenho.

## Tipos de Deploy
- All at Once (Tudo de uma vez):  É a opção mais rápida, já que todas as instâncias são atualizadas simultaneamente. Pode causar indisponibilidade durante o processo, pois não há tempo de transição ou rollback se algo der errado.
- Rolling Deployment (Implantação em lote): Atualiza as instâncias em pequenos grupos (batches) de uma vez. Ou seja, um lote de instâncias é atualizado, enquanto o restante continua rodando a versão antiga. Durante o deployment, pode haver versões diferentes da aplicação rodando em diferentes servidores.
- Rolling with Additional Batch (Rolling com lote adicional): Cria uma nova instância (ou mais, dependendo da configuração) antes de iniciar o processo de atualização. Isso garante que o número original de instâncias esteja sempre disponível, mesmo durante a atualização. Mantém a capacidade de servidores enquanto atualiza. É uma opção segura para grandes aplicações que não podem perder desempenho durante a atualização. Pode aumentar os custos momentaneamente, já que você estará rodando instâncias extras.
- Immutable Deployment (Implantação imutável): Você envia uma nova versão da aplicação, o Elastic Beanstalk prepara novas instâncias, testa e, se tudo correr bem, coloca as novas instâncias no ar, tudo isso sem que os usuários percebam ou experimentem qualquer falha. É a maneira mais segura, já que se algo der errado, o rollback é simples e rápido. É mais caro, pois envolve a criação de um novo conjunto de instâncias temporárias. Também é um processo mais lento.
- Blue/Green Deployment (Implantação Azul/Verde): Mantém dois ambientes separados: um ambiente "azul" (produção atual) e um ambiente "verde" (com a nova versão da aplicação). Depois de testar o ambiente verde, você faz um switch para direcionar o tráfego para ele. Pode ser mais complexo de gerenciar e mais caro, pois requer dois ambientes rodando ao mesmo tempo.

## LifeCycle Policy
- A Lifecycle Policy no AWS Elastic Beanstalk ajuda a gerenciar automaticamente as versões de aplicação que você carrega na sua conta, permitindo controlar o número de versões armazenadas e evitar que o repositório se encha de versões antigas. Essa política é essencial para evitar que o seu ambiente consuma muito armazenamento desnecessariamente, já que cada versão da aplicação é armazenada no Amazon S3 e pode ocupar bastante espaço ao longo do tempo.
- As versões excluídas pela política de ciclo de vida não podem ser recuperadas.

## Extensions
- Servem basicamente para customização: Instalar bibliotecas, configurar serviços, ou ajustar parâmetros do servidor para necessidades específicas da aplicação.
- Essas extensões são geralmente configuradas em arquivos com o sufixo .config e são colocadas na pasta .ebextensions dentro do seu diretório de aplicação.
- Pode ser usado para Ambientes de teste e produção diferentes

## :books: Referências
 - *https://docs.aws.amazon.com/elastic-beanstalk/*
<br />
<br />

<h1 align= "center"> 
 ☁️Developer Tools🔧 
<h1 />
  <p align= "center">
  <img src="./Icons/Arch_AWS-Amplify_64%405x.png" alt="Amplify-icon" style="height:180px; width:180px;"/>
<br />
    <h2 align="center">
Amplify 
    </h2>
</p>

O AWS Amplify facilita a criação do backend para você. Ele pode gerar automaticamente recursos como APIs, banco de dados, autenticação de usuários e armazenamento de arquivos, tudo de forma simplificada e sem precisar gerenciar servidores. Você só precisa configurar o que precisa e o Amplify cuida da parte de infraestrutura.

## Integração CI/CD
- O CI/CD do AWS Amplify não precisa de outros serviços da AWS como o CodeDeploy ou CodeBuild para funcionar. O Amplify já inclui ferramentas integradas de build e deploy, ou seja, tudo o que você precisa para configurar o fluxo de CI/CD está dentro da própria plataforma Amplify.
- O primeiro passo para configurar o CI/CD no Amplify é conectar o seu repositório de código ao serviço. Amplify suporta repositórios do GitHub, GitLab, Bitbucket e AWS CodeCommit.
- Build Automático: Sempre que você faz uma alteração no código (como um novo commit ou push para o branch monitorado), o Amplify executa automaticamente o processo de build.
- Deploy Automático: Após o build ser concluído com sucesso, o Amplify automaticamente implanta os arquivos gerados na hospedagem serverless do Amplify

## :books: Referências
 - *https://docs.amplify.aws/*
<br />
<br />

<p align= "center">
  <img src="./Icons/Arch_AWS-CloudShell_64%405x.png" alt="CloudShell-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CloudShell
    </h1>
</p>

O AWS CloudShell é um ambiente de linha de comando baseado em navegador que oferece acesso instantâneo à AWS, permitindo que você execute comandos e scripts sem precisar configurar nada localmente.

## Características
- O CloudShell vem com várias ferramentas e SDKs pré-instalados, incluindo AWS CLI, Python, Node.js, Git, AWS SAM CLI e outros, o que facilita o gerenciamento de recursos e o desenvolvimento de aplicativos sem precisar instalar nada manualmente.
- Cada usuário recebe 1 GB de armazenamento persistente para armazenar scripts, arquivos de configuração e outros dados. Isso significa que mesmo depois de você fechar a sessão, os dados permanecerão disponíveis na próxima vez que você acessar o CloudShell.
- O CloudShell permite que você abra múltiplas sessões em paralelo
- Não é ideal para executar cargas de trabalho pesadas, sendo mais adequado para tarefas de gerenciamento e desenvolvimento leve.

## Acesso
- O CloudShell usa as credenciais de segurança associadas à sua conta da AWS

# Casos de Uso
- Gerenciamento de Infraestrutura: Executar comandos para gerenciar EC2, S3, Lambda, entre outros, diretamente da linha de comando.
- Desenvolvimento e Testes rápidos: Usar as ferramentas de desenvolvimento pré-instaladas para testar e iterar rapidamente.
- Execução de Comandos Rápidos: Realizar tarefas rápidas como upload de arquivos para o S3 ou execução de comandos de rede.

## :books: Referências
 - *https://docs.aws.amazon.com/cloudshell/latest/userguide/welcome.html*
<br />
<br />

<p align= "center">
  <img src="./Icons/Arch_AWS-CodeArtifact_64%405x.png" alt="CodeArtifact-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CodeArtifact
    </h1>
</p>

O AWS CodeArtifact é como um armário na nuvem onde você guarda e compartilha as bibliotecas e pacotes de código, como uma dependência Maven para um projeto Java ou npm para um app em JavaScript, permitindo que você gerencie versões de bibliotecas.<br/ >
O serviço é completamente gerenciado e escalável, podendo lidar com um grande número de pacotes e usuários sem necessidade de manutenção de infraestrutura.

## Repositórios
- Você pode criar repositórios privados para armazenar e compartilhar pacotes dentro de sua organização, garantindo controle sobre o acesso e versões dos pacotes.

## Integração CI/CD
- CodeArtifact se integra facilmente com ferramentas de build e CI/CD, como AWS CodeBuild, Jenkins, e GitHub Actions
- CodeArtifact é integrado com outros serviços da AWS, como AWS CodePipeline, AWS Lambda, e AWS CodeBuild, permitindo uma automação de ponta a ponta no fluxo de desenvolvimento e implantação de software.

## Cache de Pacotes
- Permite que você faça cache de pacotes de repositórios públicos (como Maven Central, npm Registry, PyPI), otimizando o tempo de download e a disponibilidade das dependências.

https://docs.aws.amazon.com/codeartifact/latest/ug/

## :books: Referências
 - *https://docs.aws.amazon.com/codeartifact/latest/ug/*
<br />
<br />

<p align= "center">
  <img src="./Icons/Arch_AWS-CodeBuild_64%405x.png" alt="CodeBuild-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CodeBuild
    </h1>
</p>

O AWS CodeBuild é um serviço de Integração Contínua (CI) que automatiza o processo de compilação (build) do seu código. Ele pega o código-fonte, executa os testes e gera artefatos (como pacotes, binários ou imagens de containers)

## Estrutura de Arquivos do CodeBuild
- No código do arquivo buildspec.yml deverá conter as instruções para realizar o build. Este arquivo deve estar no diretório raiz(root directory) do seu código.
- Dependendo da linguagem ou framework que você está usando, pode haver arquivos específicos para gerenciar dependências.
- Node.js (npm): package.json e package-lock.json
- Java (Maven): pom.xml
- Python (pip): requirements.txt
- Docker: Dockerfile

## Cache
- Também é possível configurar o cache no buildspec.yml para armazenar dependências ou arquivos entre builds e acelerar a execução.

## :books: Referências
 - *https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html*
<br />
<br />

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

<p align= "center">
  <img src="./Icons/Arch_AWS-CodePipeline_64%405x.png" alt="CodePipeline-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CodePipeline
    </h1>
</p>

O AWS CodePipeline é um grande integrador do seu processo de CI/CD, como uma linha de produção automatizada. Ele pega o código que você desenvolveu do seu repositório gtiHub, gtiLab etc... passa por etapas automáticas como build, testes e deploy, e coloca ele pronto para produção. Tudo sem você precisar fazer nada manualmente! É o processo de CI/CD na prática, onde cada mudança no código passa por uma sequência de etapas controladas, garantindo que tudo seja testado e entregue!🚀✅

## Fases do seu Pipeline
- Você pode definir várias fases (como Source, Build, Test, Deploy) e dentro de cada fase, você pode configurar ações específicas (como rodar um script, executar testes, fazer deploy, etc.).

# Ações personalizadas
- O CodePipeline oferece a possibilidade de adicionar ações personalizadas no pipeline, como executar scripts, integrar com sistemas externos ou ferramentas de terceiros, ou até mesmo realizar etapas que não estão nativamente disponíveis no serviço.

# Integrações
- Integra o processo de CI/CD end-to-end
- Conexão com CodeCommit, GitHub, S3.
- Integração com CodeBuild/CodeDeploy: Permite que o código seja implantado de maneira automatizada, com suporte a estratégias de deploy como Blue/Green e Canary, e a capacidade de fazer rollback automático em caso de falhas.
- Oferece integrações com o Amazon CloudWatch e Amazon SNS o que ajuda manter o controle sobre o andamento do pipeline e a receber alertas para intervir rapidamente, caso algo dê errado.
- O CodePipeline suporta múltiplas regiões AWS, permitindo que você orquestre o deploy de código em diferentes regiões de forma simultânea. Útil para empresas que operam em várias regiões e precisam garantir que o código seja implantado de forma consistente em todas as regiões.
- É possível usar o AWS CloudFormation para definir o pipeline como código. Assim, você pode versionar, automatizar e recriar pipelines facilmente em diferentes ambientes. Facilitando a automação e a repetibilidade do processo de criação e manutenção de pipelines, especialmente em ambientes de grandes empresas com múltiplas equipes.

# Rollbacks
- O CodePipeline pode automaticamente realizar rollback (voltar para uma versão anterior) caso uma etapa falhe, como no caso de um deploy que não funcione como esperado.

# Versionamento
- O CodePipeline oferece controle de versões para que você possa revisar e rastrear cada versão do código que passou por seu pipeline.

## :books: Referências
 - *https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html*
<br />
<br />

<p align= "center">
  <img src="./Icons/Arch_AWS-X-Ray_64%405x.png" alt="X-Ray-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
X-Ray
    </h1>
</p>

Imagine que você tem uma aplicação complexa com várias partes conversando entre si (como APIs, bancos de dados, ou microservices). O X-Ray pega tudo isso, cria um mapa visual, e te mostra passo a passo o que está acontecendo, quanto tempo cada parte levou e onde estão os gargalos. Isso pode ser feito usando SDKs do X-Ray para diferentes linguagens (como Java, Node.js, Python, etc.) ou via AWS SDK para serviços integrados como Lambda, EC2, ECS, API Gateway, etc.


## Como integrar o X-RAY ao seu código
- A primeira etapa para usar o X-Ray é instrumentar seu código com o SDK do X-Ray. Isso envolve a inclusão de bibliotecas no seu código-fonte para que o X-Ray consiga coletar as informações de rastreamento.
- Configuração do Daemon: O Daemon do X-Ray deve ser executado em suas instâncias EC2 ou containers, para coletar e enviar os dados de rastreamento.
- Configuração do Console: Você pode acessar e analisar as informações diretamente no console do X-Ray, onde poderá ver as métricas, gráficos e rastreamentos de todas as requisições.

## Casos de Uso
- Diagnóstico de Erros: Se algo der errado em sua aplicação, você pode usar o X-Ray para rastrear o fluxo da requisição e entender onde o erro ocorreu.
- Otimização de Desempenho: O X-Ray pode identificar pontos lentos na aplicação, ajudando a otimizar o desempenho de cada serviço.
- Monitoramento de Aplicações Complexas: Ideal para aplicações distribuídas e baseadas em microserviços, o X-Ray facilita o monitoramento de serviços interdependentes.

## Limitações
- Por padrão, os rastreamentos são armazenados por até 30 dias.
- O uso do X-Ray pode gerar custos adicionais, então é importante monitorar a quantidade de dados sendo coletada e armazenada.

## :books: Referências
 - *https://docs.aws.amazon.com/xray/*
<br />
<br />
<h1 align= "center">
<p align= "center">
  <img src="./Icons/Arch_AWS-Command-Line-Interface_64%405x.png" alt="CLI-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CLI
    </h1>
</p>

Ah, o AWS CLI! 🖥️ é "o controle remoto" da AWS que você usa direto no terminal. Sabe quando você quer mexer na sua conta da AWS, mas não está com paciência para ficar clicando em botões na interface gráfica? É aí que o CLI brilha!<br>
CLI significa Command Line Interface. É um programa que você instala no seu computador e que te permite controlar e interagir com todos os serviços da AWS usando comandos de texto. Com ele, você pode fazer quase tudo o que faria no console da AWS, só que mais rápido e de maneira automatizada.

## Como começar
- Ao contrário do CloudShell, o CLI precisa ser instalado na sua máquina
- Com o CLI intalado vc precisa configurar sua credenciais para começar usar. Só digitar o comando **aws configure** e adicionar a secret key e Acess Key 
- Região padrão: Como us-east-1 ou sa-east-1.
- Formato de saída: JSON, text ou table.

## Comando
- Os comando no AWS CLI tem 3 partes principais aws <serviço> <ação> [opções]. Exemplo aws s3 ls

## Multi Contas
- O AWS CLI suporta multi-contas usando perfis nomeados. Isso é útil para gerenciar diferentes ambientes ou contas, como desenvolvimento, teste e produção, sem precisar reconfigurar suas credenciais a cada vez que muda de conta.
- Você pode configurar múltiplos perfis no AWS CLI através do comando aws configure com a opção --profile. aws configure --profile perfil1

## Principais Comandos
| **Serviço**               | **Comando**                                                                                                 | **Descrição**                                                                                      |
|---------------------------|-------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| **Geral**                  | `aws --version`                                                                                             | Verifica a versão do AWS CLI                                                                       |
|                           | `aws configure`                                                                                             | Configura o perfil do AWS CLI (credenciais, região e formato de saída)                            |
|                           | `aws help`                                                                                                  | Lista os serviços disponíveis da AWS                                                              |
|                           | `aws <serviço> help`                                                                                         | Exibe ajuda para um comando específico                                                            |
| **EC2 (Elastic Compute Cloud)** | `aws ec2 describe-instances`                                                                              | Lista instâncias EC2                                                                              |
|                           | `aws ec2 start-instances --instance-ids <instance-id>`                                                      | Inicia uma instância EC2                                                                          |
|                           | `aws ec2 stop-instances --instance-ids <instance-id>`                                                       | Para uma instância EC2                                                                            |
|                           | `aws ec2 run-instances --image-id <ami-id> --count 1 --instance-type t2.micro --key-name <key-pair-name>`    | Cria uma nova instância EC2                                                                       |
|                           | `aws ec2 describe-security-groups`                                                                          | Lista grupos de segurança                                                                         |
| **S3 (Simple Storage Service)** | `aws s3 mb s3://<nome-do-bucket>`                                                                         | Cria um novo bucket no S3                                                                          |
|                           | `aws s3 ls s3://<nome-do-bucket>`                                                                            | Lista arquivos em um bucket S3                                                                    |
|                           | `aws s3 cp <arquivo-local> s3://<nome-do-bucket>/<caminho-do-arquivo>`                                       | Copia um arquivo para o bucket S3                                                                  |
|                           | `aws s3 sync <diretório-local> s3://<nome-do-bucket>/<diretório-destino>`                                   | Sincroniza diretórios locais com um bucket S3                                                      |
|                           | `aws s3 rm s3://<nome-do-bucket>/<caminho-do-arquivo>`                                                      | Exclui um arquivo de um bucket S3                                                                  |
| **IAM (Identity and Access Management)** | `aws iam list-users`                                                                                     | Lista usuários IAM                                                                                |
|                           | `aws iam create-user --user-name <nome-do-usuário>`                                                          | Cria um usuário IAM                                                                               |
|                           | `aws iam attach-user-policy --user-name <nome-do-usuário> --policy-arn arn:aws:iam::aws:policy/<nome-da-política>` | Atribui uma política IAM a um usuário                                                             |
|                           | `aws iam delete-user --user-name <nome-do-usuário>`                                                          | Deleta um usuário IAM                                                                              |
| **RDS (Relational Database Service)** | `aws rds describe-db-instances`                                                                             | Lista instâncias RDS                                                                               |
|                           | `aws rds create-db-instance --db-instance-identifier <nome-instancia> --db-instance-class db.t2.micro --engine mysql --master-username <nome-usuario> --master-user-password <senha> --allocated-storage 20` | Cria uma instância de banco de dados RDS                                                           |
|                           | `aws rds delete-db-instance --db-instance-identifier <nome-instancia>`                                       | Exclui uma instância RDS                                                                           |
| **Lambda**                 | `aws lambda list-functions`                                                                                 | Lista funções Lambda                                                                               |
|                           | `aws lambda create-function --function-name <nome-da-função> --runtime nodejs14.x --role arn:aws:iam::<account-id>:role/<role-name> --handler index.handler --zip-file fileb://function.zip` | Cria uma função Lambda                                                                              |
|                           | `aws lambda invoke --function-name <nome-da-função> output.txt`                                              | Invoca uma função Lambda                                                                            |
| **CloudWatch**             | `aws logs describe-log-groups`                                                                               | Lista grupos de logs do CloudWatch                                                                 |
|                           | `aws cloudwatch put-metric-data --namespace <namespace> --metric-name <nome-da-métrica> --value <valor>`      | Cria uma métrica personalizada no CloudWatch                                                       |
|                           | `aws cloudwatch list-metrics`                                                                                | Lista as métricas no CloudWatch                                                                    |
| **CloudFormation**         | `aws cloudformation create-stack --stack-name <nome-da-stack> --template-body file://template.json`          | Cria uma stack no CloudFormation                                                                   |
|                           | `aws cloudformation describe-stacks`                                                                         | Lista stacks no CloudFormation                                                                     |
|                           | `aws cloudformation delete-stack --stack-name <nome-da-stack>`                                               | Exclui uma stack no CloudFormation                                                                  |
| **SNS (Simple Notification Service)** | `aws sns list-topics`                                                                                       | Lista tópicos SNS                                                                                 |
|                           | `aws sns create-topic --name <nome-do-tópico>`                                                                | Cria um tópico SNS                                                                                 |
|                           | `aws sns publish --topic-arn <arn-do-tópico> --message "Mensagem de teste"`                                   | Publica uma mensagem em um tópico SNS                                                              |
| **SQS (Simple Queue Service)** | `aws sqs list-queues`                                                                                       | Lista filas SQS                                                                                   |
|                           | `aws sqs create-queue --queue-name <nome-da-fila>`                                                            | Cria uma fila SQS                                                                                 |
|                           | `aws sqs send-message --queue-url <url-da-fila> --message-body "Texto da mensagem"`                          | Envia uma mensagem para uma fila SQS                                                               |
|                           | `aws sqs receive-message --queue-url <url-da-fila>`                                                           | Recebe mensagens de uma fila SQS                                                                   |
| **Route 53**               | `aws route53 list-hosted-zones`                                                                              | Lista zonas hospedadas no Route 53                                                                  |
|                           | `aws route53 create-hosted-zone --name example.com --caller-reference <referência-única>`                    | Cria uma zona hospedada no Route 53                                                                |
|                           | `aws route53 change-resource-record-sets --hosted-zone-id <zona-id> --change-batch file://change-batch.json` | Adiciona um registro DNS em uma zona hospedada no Route 53                                         |

## :books: Referências
 - *https://docs.aws.amazon.com/cli/*
<br />
<br />

<p align= "center">
  <img src="./Icons/Arch_AWS-Tools-and-SDKs_64%405x.png" alt="SDK-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
SDK
    </h1>
</p>

O AWS SDK é uma biblioteca de programação que você integra em seu código-fonte (em várias linguagens, como Python, Java, JavaScript, etc.) para interagir com os serviços da AWS. <br>
- O exame cobra tanto a compreensão teórica de como esses serviços funcionam quanto a capacidade prática de usar o AWS SDK para interagir com esses serviços programaticamente.
- Para se preparar para a certificação, além de aprender sobre esses serviços, é importante praticar escrevendo código que interaja com a AWS usando o SDK, pois isso reflete os tipos de habilidades que o exame exige.


## Linguagens suportadas
- Java
- Python (Boto3)
- JavaScript (Node.js)
- Ruby
- C#
- Go
- PHP
- .NET
- Swift (para desenvolvimento iOS)

## Como usar
- Para começar a usar o AWS SDK, você precisa instalá-lo no seu ambiente de desenvolvimento.
- O SDK lida automaticamente com a autenticação, utilizando as credenciais configuradas através do AWS CLI ou variáveis de ambiente. Ele também pode gerenciar sessões temporárias usando o AWS STS (Security Token Service) para gerar credenciais temporárias.
- O SDK roda dentro do seu código de aplicativo, não diretamente no terminal como o CLI.

## Exemplos de Uso do SDK
- Interação com Amazon S3 (Simple Storage Service): operações para criar, listar, carregar e excluir objetos em um bucket S3.
```python
import boto3

# Criando um cliente do S3
s3 = boto3.client('s3')

# Carregar um arquivo no S3
s3.upload_file('meuarquivo.txt', 'meu-bucket', 'meuarquivo.txt')

# Listar objetos de um bucket
response = s3.list_objects_v2(Bucket='meu-bucket')
for obj in response['Contents']:
    print(obj['Key'])

```
<br>

- Interação com AWS Lambda: invocar funções Lambda e passar dados para elas.

```python
import boto3

# Criando um cliente Lambda
lambda_client = boto3.client('lambda')

# Invocando uma função Lambda
response = lambda_client.invoke(
    FunctionName='MinhaFuncaoLambda',
    InvocationType='RequestResponse',  # Pode ser 'Event' para assíncrono
    Payload='{"chave": "valor"}'
)

# Exibir a resposta
print(response['Payload'].read().decode('utf-8'))

```

## :books: Referências
 - *https://docs.aws.amazon.com/sdk/*
<br />
<br />

<p align= "center">
  <img src="./Icons/Arch_AWS-Cloud-Development-Kit_64%405x.png" alt="SDK-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
SDK
    </h1>
</p>

O AWS CDK (Cloud Development Kit) é uma ferramenta que permite criar e gerenciar recursos na AWS usando linguagens de programação que você já conhece, como TypeScript, Python, Java, C#, e Go. É uma abordagem moderna e poderosa para implementar infraestrutura como código (IaC), substituindo arquivos YAML ou JSON complicados por código mais legível e reutilizável. <br>

Pense nele como uma forma de "codificar sua infraestrutura" com a mesma facilidade que você desenvolve uma aplicação. Legal, né? 😎

## Por onde começar
- O CDK precisa ser instalado npm install -g aws-cdk
- Crie um Novo Projeto cdk init app --language python 
- Escreva seu Código de Infraestrutura: O arquivo principal (app.py) contém sua infraestrutura.

```python
from aws_cdk import core, aws_s3 as s3

class MeuStack(core.Stack):
    def __init__(self, scope: core.Construct, id: str, **kwargs) -> None:
        super().__init__(scope, id, **kwargs)

        # Criar um bucket S3
        s3.Bucket(self, "MeuBucket", versioned=True)
```
- Deploy Automático: Com um único comando, você cria ou atualiza sua infraestrutura: cdk deploy

## Funcionamento
- CDK Gera CloudFormation: O código que você escreveu é transformado em um template CloudFormation, que a AWS usa para criar e gerenciar os recursos.

## Componentes
- App: É o ponto de entrada do seu código CDK
- Stack: Representa uma unidade lógica de infraestrutura (equivalente a um stack no CloudFormation).
- Constructs: Blocos básicos usados para criar recursos. Existem três tipos principais:
<br>
L1 (Low-level Constructs): Representam diretamente os recursos do CloudFormation.
L2 (High-level Constructs): Abstrações simplificadas, como criar buckets S3 com configurações padrão.
L3 (Patterns): Conjuntos de recursos pré-configurados para cenários específicos (ex.: aplicações web serverless).

## :books: Referências
 - *https://docs.aws.amazon.com/cdk/*
<br />
<br />

 💼Gerenciamento e Governança📜
<h1 />

## Como Usar Este Repositório 🧑‍💻

1. **Navegação pelos Tópicos**: Cada diretório contém materiais específicos sobre um determinado serviço ou conceito. Abra os arquivos `.md` para ler os resumos, entender os conceitos principais e acessar links para mais detalhes, como a documentação oficial da AWS.
2. **Exemplos de Código**: Alguns tópicos contêm exemplos de código prontos para você experimentar e entender como integrar os serviços da AWS em seus próprios projetos.
3. **Atualizações Regulares**: Este repositório será atualizado constantemente com novos conteúdos, links úteis e exemplos para garantir que você tenha as informações mais recentes sobre a certificação.

## Contribuindo 🤝

Este repositório é colaborativo! Se você tem sugestões, correções ou novos materiais que gostaria de adicionar, fique à vontade para abrir uma **issue** ou enviar um **pull request**.

### Como Contribuir:

1. **Faça um fork do repositório**.
2. **Crie um branch** para a sua contribuição.
3. **Faça suas alterações** e **comite** suas mudanças.
4. **Envia um pull request** explicando o que foi alterado.

## Licença 📜

Este repositório é licenciado sob a [MIT License](https://opensource.org/licenses/MIT). Sinta-se livre para usar e contribuir com o conteúdo.

## Referências 🌐
- [Documentação Oficial da AWS](https://aws.amazon.com/documentation/)
- [AWS Certified Developer - Associate Exam Guide](https://aws.amazon.com/certification/certified-developer-associate/)

## Contato 📬

Se você tiver alguma dúvida ou sugestão, sinta-se à vontade para abrir uma **issue** ou entrar em contato através do GitHub.

---

**Boa sorte nos seus estudos e no exame de certificação!** 🎓🚀

