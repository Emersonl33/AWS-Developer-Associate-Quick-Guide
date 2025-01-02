<p align= "center">
  <img src="./Icons/Arch_Amazon-CloudWatch_64%405x.png" alt="CloudWatch-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Cloud Watch
    </h1>
</p>

O CloudWatch é o cérebro de monitoramento da AWS. Ele coleta métricas, logs e eventos, permitindo que você entenda o comportamento de suas aplicações, tome decisões baseadas em dados e automatize respostas a eventos importantes.

## Tipos de métricas
- Métricas Padrão (Standard Metrics): Essas métricas são coletadas automaticamente por muitos serviços da AWS e não exigem configuração adicional.
- Métricas Personalizadas (Custom Metrics): Essas métricas são criadass pelo usuário e podem ser enviadas para o CloudWatch para monitorar aspectos específicos de suas aplicações ou recursos que não estão cobertos pelas métricas padrão.<br>
Exemplo: Monitorar o número de erros em uma aplicação, taxa de sucesso de transações, ou métricas de negócios como "número de vendas". Você pode enviar essas métricas usando o AWS CLI, SDKs ou APIs.
- Métricas de Monitoramento Detalhado (Detailed Monitoring Metrics): Por padrão, muitos recursos da AWS, como EC2, fornecem métricas com intervalos de 5 minutos. No entanto, você pode ativar o monitoramento detalhado, que oferece métricas com intervalos de 1 minuto. Isso é útil para obter visibilidade mais granular em seu sistema.

## Alarmes
- Um Alarme do CloudWatch permite que você defina uma condição específica em relação a uma métrica, e o CloudWatch monitora constantemente essa métrica.
- Componentes de um alarme:<br>
Métrica: O dado que está sendo monitorado, como uso de CPU, tráfego de rede, ou memória disponível.<br>
Threshold (Limite): O valor ou condição que você quer monitorar. Pode ser um número fixo (por exemplo, 80% de uso de CPU) ou baseado em uma fórmula.<br>
Período: O intervalo de tempo que o alarme irá observar. Pode ser um valor fixo, como 5 minutos, 1 hora, etc.<br>
Estatísticas: O tipo de estatísticas a serem usadas para comparar a métrica<br>
Ações: O que o alarme fará quando o limite for alcançado (como enviar uma notificação ou acionar uma função Lambda).
- Custo: O CloudWatch cobra por alarme criado. A AWS oferece uma quantidade gratuita de alarmes por mês, mas, se você criar mais alarmes, será cobrado por eles.<br>
alarmes Padrão custa $0,10 por alarme por mês (após o limite de 10 alarmes gratuitos).<br>
Se o alarme acionar uma notificação via SNS (Simple Notification Service), você será cobrado pelo envio de mensagens SNS.<br>
Se o alarme acionar outras ações, como execução de funções Lambda ou alterações no Auto Scaling, você também pode incorrer em custos adicionais dependendo do serviço acionado.

## CloudWatch Logs
- O CloudWatch Logs coleta logs de diversos recursos na AWS, como:<br>
EC2: Logs de sistema, aplicação, ou logs de instâncias.<br>
Lambda: Logs de execução das funções Lambda.<br>
VPC Flow Logs: Registros de tráfego de rede dentro de uma VPC.<br>
CloudTrail: Registros de chamadas de API na AWS.<br>
- Alarmes Baseados em Logs: Você pode configurar alarmes para ser notificado de eventos específicos que ocorram nos logs.
- Filtros de Logs: Você pode aplicar filtros em seus logs para encontrar padrões, como erros ou exceções.

## CloudWatch Logs Insights
- O CloudWatch Logs Insights permite escrever consultas usando uma linguagem semelhante ao SQL, facilitando a extração de informações relevantes dos logs.
- As consultas podem gerar gráficos e tabelas para visualizar os resultados
- O CloudWatch Logs Insights permite que você consulte log groups específicos ou várias fontes de logs ao mesmo tempo, o que ajuda a analisar dados de diferentes serviços (como Lambda, EC2, etc.) em um único lugar.

## Sintaxe e Operações Comuns em CloudWatch Logs Insights
- fields: Especifica quais campos dos logs você quer exibir.
- filter: Aplica um filtro de busca. Pode ser usado para procurar por palavras-chave, padrões de regex, etc.
- stats: Realiza cálculos agregados, como contagens, somas, médias, máximos, etc.
- parse: Utilizado para extrair dados estruturados de campos de log, como extrair números de uma string de log.
- sort: Ordena os resultados, podendo ser em ordem crescente ou decrescente.
- limit: Limita o número de resultados retornados pela consulta.

Exibir a duração das funções Lambda:
```sql
fields @timestamp, @message
| filter @message like /REPORT/
| parse @message "Duration: * ms" as duration
| stats avg(duration) by bin(1h)

```

Verificar o tráfego de rede por IP:
```sql
fields @timestamp, @message
| filter @message like /Received/
| parse @message "sourceIp: *" as source_ip
| stats count() by source_ip
```

## Comandos CLI
- put-metric-data: Envia dados de métricas personalizados para o CloudWatch. Com isso, você pode monitorar métricas específicas que não são fornecidas automaticamente pelos recursos da AWS.<br>
aws cloudwatch describe-alarms --alarm-name "MyAlarm"
- describe-alarms: Obtém informações sobre alarmes do CloudWatch. Você pode usar esse comando para listar os alarmes existentes ou consultar alarmes específicos.<br>
aws cloudwatch describe-alarms
- set-alarm-state: Altera o estado de um alarme manualmente. Isso pode ser útil para testes ou para simular mudanças no estado de um alarme.<br>
aws cloudwatch set-alarm-state --alarm-name "MyAlarm" --state-value "ALARM" --state-reason "Testing"

## :books: Referências
 - *https://docs.aws.amazon.com/cloudwatch/*
<br />
<br />