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