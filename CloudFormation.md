<p align= "center">
  <img src="./Icons/Arch_AWS-CloudFormation_64%405x.png" alt="CloudFormation-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Cloud Formation
    </h1>
</p>

O AWS CloudFormation é um serviço da AWS que ajuda você a criar e gerenciar sua infraestrutura na nuvem usando código declarativo. Em vez de configurar manualmente recursos como servidores, bancos de dados ou redes, você define tudo em um arquivo YAML ou JSON. <br>
Pense no CloudFormation como o "pedreiro" da sua infraestrutura na AWS: você escreve o projeto, e ele constrói a casa. 🏗️

## Como Funciona
- Template: Você cria um arquivo YAML ou JSON chamado template, que descreve os recursos que você quer na AWS (ex.: S3, EC2, RDS).
- Stack: O CloudFormation usa o template para criar um stack, que é um grupo de recursos que são gerenciados como uma única unidade.
- Automação e Gerenciamento: O CloudFormation configura os recursos na ordem correta, resolve dependências automaticamente e permite atualizações ou exclusão do stack inteiro.
- 

## Principais Conceitos
- Template: É o "plano" da sua infraestrutura. Contém seções como: <br>
Resources: Lista de recursos a serem criados.<br>
Parameters: Variáveis que tornam o template reutilizável.<br>
Outputs: Informações que o stack retorna após ser criado <br>
- Exemplo de template básico:
```yaml
Resources:
  MyBucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: meu-bucket-exemplo
```
- Stack: Um stack é a materialização de um template. Tudo que o template define será criado dentro do stack.
- Change Sets: Antes de atualizar um stack, o CloudFormation cria um Change Set (simulação das alterações) para você revisar.
- Drift Detection: Permite verificar se os recursos do stack foram alterados manualmente e estão "fora de sincronia" com o template original.

## Tipos de Stacks
- Nested Stacks: Stacks aninhados permitem modularizar sua infraestrutura. Melhora a organização de projetos grandes. Facilita a reutilização de recursos.
- Cross-Stack References: Permite que um stack compartilhe recursos com outro. Usa Exports e Imports para passar informações de um stack para outro. O stack "Rede" exporta o ID de uma VPC, e o stack "Aplicação" importa essa VPC para usar na configuração de instâncias EC2.
- StackSets: Permite criar, atualizar e gerenciar stacks em múltiplas contas ou regiões. Ideal para organizações que precisam de infraestrutura padronizada em ambientes distribuídos.

## Como subir uma Stack:
- Validação do template: **aws cloudformation validate-template --template-body file://template.yaml**
- Criação do bucket S3 (se necessário): **aws s3 mb s3://meu-bucket-deploy**
- Empacotar o template (se necessário): **aws cloudformation package --template-file template.yaml --s3-bucket meu-bucket-deploy --output-template-file template-packaged.yaml**
- Criar a stack: **aws cloudformation create-stack --stack-name MeuStack --template-body file://template.yaml**
- Monitorar o progresso: **aws cloudformation describe-stack-events --stack-name MeuStack**
- Atualizar a stack: **aws cloudformation update-stack --stack-name MeuStack --template-body file://novo-template.yaml**
- Excluir a stack: **aws cloudformation delete-stack --stack-name MeuStack**

## :books: Referências
 - *https://docs.aws.amazon.com/cloudformation/*
<br />
<br />