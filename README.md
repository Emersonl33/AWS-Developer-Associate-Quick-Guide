# AWS Certified Developer Associate - Study Guide 📚☁️

Esse repositório é um rodmap com os pontos mais importantes de todo conteúdo que consumi durante minha preparação para a certificação **AWS Developer Associate**.
<br>
A idéia é trazer um guia de estudos com conceitos fundamentais sobre o que é cobrado no exame.
- **O repositório está organizado por tópicos e serviços relevantes para a certificação, todo conteúdo está contido nesse README e também pode ser acessado pelos arquivos .md**

## Sobre o Exame 🎯

A certificação **AWS Certified Developer Associate** tem como objetivo validar seus conhecimentos sobre ferramentas de desenvolvimento dentro da AWS. Para essa certificação é recomendado que você tenha pelo menos 1 ano de exeperiência com desenvolvimento na AWS. 
Isso pode ser adquirido por meio de labs práticos disponíveis no skillbuilder https://aws.amazon.com/pt/training/digital/ ou por meio de projetos profissionais e pessoais livres. Abuse do Free Tier para experimentar os recursos. <br>
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

<h1 align= "center"> 
  Segurança e Identidade🔒 
</h1>
<p align= "center">
  <img src="./icons/aws-IAM.png" alt="IAM-icon" style="height:120px; width:120px;"/>
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

## Referência: https://docs.aws.amazon.com/pt_br/IAM/latest/UserGuide/introduction.html

<br>
<br>

<p align= "center">
  <img src="./icons/aws-Cognito.png" alt="COGNITO-icon" style="height:120px; width:120px;"/>
<br />
    <h3 align="center">
COGNITO
    </h3>
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


## Referência: *https://docs.aws.amazon.com/pt_br/cognitoidentity/latest/APIReference/Welcome.html*
<br />
<br />

<h1 align= "center"> 
  🖥️ Computação
</h1>
<p align= "center">
  <img src="./icons/aws-IAM.png" alt="EC2-icon" style="height:120px; width:120px;"/>
<br />
    <h2 align="center">
IAM
    </h2>
</p>


- [EC2](EC2.md) 💻
- 
- [Lambda](Lambda.md) 🔧
- [ECS](ECS.md) 🐋
- [EKS](EKS.md) 🛞

### 🖥️ ****Desenvolvimento (32%)****

- [API Gateway](API-Gateway.md) 🌐
- [Lambda](Lambda.md) λ
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

### 🛠️ **Ferramentas de Desenvolvimento**


### ⚡ **Eventos e Integração**

- [EventBridge](EventBridge.md) 🌩️
  
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

