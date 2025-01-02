<p align= "center">
  <img src="./Icons/Arch_Amazon-EventBridge_64%405x.png" alt="Event-Bridge-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Event Bridge
    </h1>
</p>

O Amazon EventBridge é um serviço da AWS que facilita a criação de arquiteturas de eventos e integrações entre diferentes aplicações, sistemas e serviços de forma desacoplada e em tempo real. Ele é uma evolução do Amazon CloudWatch Events e foi projetado para fornecer uma maneira mais robusta e flexível de gerenciar eventos em grande escala.
- O EventBridge funciona através de eventos e regras. Um evento é uma mudança ou atividade que acontece em uma aplicação, serviço ou sistema. O EventBridge pode pegar esses eventos, aplicar regras para determinar o que fazer com eles, e então enviá-los para destinos como funções AWS Lambda, SQS, SNS, Kinesis, entre outros.
- O Amazon EventBridge fornece uma API robusta para interação com eventos e regras. A API pode ser usada com o AWS SDK em várias linguagens de programação, ou diretamente com a AWS CLI para automação de processos.

## Event Bus 
- Um event bus é o "canal" por onde os eventos são enviados e processados. Quando você cria um event bus personalizado, ele pode receber eventos de fontes externas e de suas próprias aplicações.
- API Reference: *CreateEventBus*
- Exemplo SDK em Python - Boto3):

``` python
import boto3

client = boto3.client('events')

response = client.create_event_bus(
    Name='my-custom-event-bus'
)
print(response)

```

## Rules
- Rules: As regras são usadas para filtrar eventos e especificar as ações a serem realizadas quando um evento corresponder à condição da regra. Elas podem direcionar eventos para destinos como Lambda, SQS, SNS, entre outros.
- API Reference: PutRule. Cria ou atualiza uma regra de evento no EventBridge.
- Exemplo SDK em Python - Boto3):

``` python
import boto3

client = boto3.client('events')

response = client.put_rule(
    Name='my-event-rule',
    EventPattern='{"source": ["aws.ec2"]}',  # Filtra eventos da EC2
    State='ENABLED',
    Description='Regras para eventos da EC2'
)
print(response)

```
## Casos de uso
- Desacoplamento de Sistemas: O EventBridge permite que diferentes partes de uma aplicação ou diferentes aplicações se comuniquem sem estarem fortemente acopladas. Por exemplo, uma aplicação de pedidos pode enviar eventos sobre o status do pedido para uma função Lambda, que pode, por sua vez, disparar uma notificação para o cliente via SNS.
- Integração de Aplicações e Serviços: EventBridge facilita a integração de várias fontes e sistemas. Você pode integrar serviços AWS, suas próprias aplicações e até mesmo serviços externos, como aplicativos SaaS

## :books: Referências
 - *https://docs.aws.amazon.com/pt_br/eventbridge/?id=docs_gateway*
<br />
<br />
