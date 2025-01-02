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






