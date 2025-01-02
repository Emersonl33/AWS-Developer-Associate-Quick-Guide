<p align= "center">
  <img src="./Icons/Arch_AWS-AppConfig_64%405x.png" alt="CloudTrail-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CloudTrail
    </h1>
</p>

CloudTrail é um serviço da AWS que permite registrar, monitorar e auditar todas as ações realizadas em sua conta da AWS. Em outras palavras, ele mantém um "registro" de todas as atividades feitas pelos usuários, aplicações ou serviços dentro da AWS, como criação, modificação ou exclusão de recursos. <br>

Cada vez que alguém realiza uma ação, como lançar uma instância EC2, criar um bucket no S3 ou modificar uma política IAM, o CloudTrail cria um log dessa ação, armazenando informações detalhadas como <br>
- Quem fez a ação (usuário ou serviço).
- O que foi feito (ação realizada, como "CreateInstance", "PutObject", etc.).
- Quando foi feito (data e hora da ação).
- Onde foi feito (região da AWS onde a ação ocorreu).
- Detalhes adicionais (ex: parâmetros usados na ação).

## Quando usar?
- Esse serviço pode ser facilmente confundido com alguns casos de uso do cloudWatch e o exame vai testar se você tem clareza sobre essas diferenças em quase todas perguntas sobre logs e auditoria.
- CloudTrail é auditório, rastreando quem fez o quê, quando e onde em sua conta AWS.
- CloudWatch é útil para monitoramento de desempenho, rastreando como os recursos estão se comportando em tempo real (uso de CPU, memória, latência, etc.).

| **Característica**               | **AWS CloudTrail**                         | **AWS CloudWatch**                          |
|-----------------------------------|--------------------------------------------|--------------------------------------------|
| **Objetivo Principal**            | Auditoria e Registro de Ações              | Monitoramento de Desempenho e Logs         |
| **Tipo de Dados**                 | Registros de chamadas de API (eventos)     | Métricas de desempenho e logs em tempo real |
| **O que é monitorado**            | Ações feitas por usuários e serviços (ex: criação de recursos, modificações) | Desempenho e métricas de recursos e logs de aplicações |
| **Exemplo de Uso**                | Investigar quem apagou um bucket S3        | Monitorar o uso de CPU de uma instância EC2 |
| **Tipo de Alertas**               | Não é voltado para alertas de desempenho; foco em auditoria de ações | Alertas de desempenho (ex: CPU, memória) e falhas de sistema |
| **Monitoramento em Tempo Real**   | Não monitoramento em tempo real. Foco em **auditoria posterior** | Monitoramento em tempo real de métricas e logs |
| **Armazenamento**                 | Logs armazenados em S3 ou CloudTrail       | Logs e métricas armazenados no CloudWatch Logs e Metrics |

## :books: Referências
 - *https://docs.aws.amazon.com/cloudtrail/*
<br />
<br />