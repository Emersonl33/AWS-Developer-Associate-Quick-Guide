<p align= "center">
  <img src="./Icons/Arch_AWS-Cloud-Development-Kit_64%405x.png" alt="SDK-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CDK
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
L1 (Low-level Constructs): Representam diretamente os recursos do CloudFormation.<br>
L2 (High-level Constructs): Abstrações simplificadas, como criar buckets S3 com configurações padrão.<br>
L3 (Patterns): Conjuntos de recursos pré-configurados para cenários específicos (ex.: aplicações web serverless).<br>

## :books: Referências
 - *https://docs.aws.amazon.com/cdk/*
<br />
<br />