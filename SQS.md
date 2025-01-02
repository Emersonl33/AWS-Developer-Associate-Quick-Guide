<p align= "center">
  <img src="./Icons/Arch_Amazon-Simple-Queue-Service_64%405x.png" alt="SQS-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
SQS
    </h1>
</p>

O SQS (Simple Queue Service) é serviço fundamental para desenvolvimento dentro da AWS. Ele funciona como uma fila de espera para mensagens. Ele ajuda a enviar dados de forma assíncrona (Não espera que o processamento de uma mensagem termine para que incie outro), desacoplando os sistemas que produzem e consomem esses dados. Ele pode ser útil para desacoplar sistemas monolitos e servir como uma camada de buffer entre um backend e frontend, por exmplo.<br>
- Ideal para processar tarefas em segundo plano, distribuir cargas de trabalho e garantir que nada se perca, mesmo em caso de falhas temporárias.
- Imagine que você tem um site de e-commerce e deseja enviar um e-mail para o cliente após a compra ser concluída
- O site de e-commerce coloca uma mensagem na fila do SQS quando o pedido for finalizado.
- Um serviço de envio de e-mails (pode ser o AWS SES) pega essa mensagem da fila, processa e envia o e-mail para o cliente. O SQS garante que a mensagem seja entregue, mesmo se o serviço de envio de e-mails estiver temporariamente indisponível.

## Componentes
- Produtor de mensagens: Um sistema (chamado "produtor") envia uma mensagem para o SQS. ***Um aplicativo de e-commerce envia uma mensagem para a fila quando um novo pedido é feito.***
- Fila: O SQS armazena as mensagens na fila até que outro sistema (chamado "consumidor") as leia e processe. ***As mensagens podem ficar na fila até serem lidas e processadas.***
- Consumidor de mensagens: Outro sistema (chamado "consumidor") pega as mensagens da fila e processa. ***Um sistema de gerenciamento de pedidos pega as mensagens da fila para processar o pedido (confirmar, separar, etc.).***

## Pooling
- Processo de um consumidor (um sistema que processa mensagens) verificando a fila para ver se há novas mensagens para processar. Existem dois tipos principais de polling: long polling e short polling.
- Long Polling (Polling Longo): O long polling é mais eficiente. E é o que já vem configurado como default. Quando o consumidor faz a consulta, ele espera por um tempo (até 20 segundos, por padrão) por uma mensagem, em vez de fazer várias consultas rápidas, se uma mensagem chegar nesse período, ela é retornada imediatamente, se não houver mensagens, a consulta é encerrada após o tempo limite.
- Short Polling (Polling Curto): O short polling ocorre quando o consumidor faz uma consulta rápida à fila para verificar se há novas mensagens. Se não houver mensagens, a resposta é retornada imediatamente, mesmo que a fila esteja vazia. Útil em cenários onde é necessário resposta rápida e constante. Pode resultar em consultas desnecessárias à fila, gerando mais custo e uso de recursos, pois o consumidor verifica a fila repetidamente, mesmo quando ela está vazia.

## Filas Standard
- Ordem das Mensagens: Não garantida (pode ser reordenada)
- Suporta alta taxa de mensagens. Não há um limite específico de throughput para filas Standard; elas são escaláveis e podem lidar com uma quantidade muito alta de mensagens simultaneamente.
- As mensagens podem ser retidas na fila por até 14 dias, mas o padrão é de 4 dias. Após esse período, as mensagens são automaticamente removidas da fila.

## Filas FIFO
- O SQS FIFO (First-In, First-Out) é um tipo de fila no Amazon Simple Queue Service (SQS) projetado para garantir que as mensagens sejam processadas na ordem exata em que foram enviadas.
- As filas FIFO têm uma limitação de throughput. Por padrão, uma fila FIFO pode processar até 300 mensagens por segundo se não houver batching (envio de mensagens em lotes).

## Dead Letter Queue (DLQ)
- Se uma mensagem falhar repetidamente (por exemplo, devido a erros no sistema ou falhas temporárias), em vez de ser descartada ou perdida, ela pode ser enviada para uma Dead Letter Queue. Isso permite que você investigue o que deu errado com essas mensagens, analisando-as separadamente, para entender a causa da falha e tomar as devidas ações.
- A DLQ é uma fila normal que precisa ser atrelada a outra fila e configurada como DLQ.

## Criando uma DLQ 
- Crie a fila principal onde as mensagens serão inicialmente enviadas.
- Crie uma fila normal que será usada como a DLQ
- Associe a DLQ à fila principal e defina o número máximo de tentativas antes que a mensagem seja movida para a DLQ.

## Problemas Comuns (Isso aqui cai muito kkkkk)
- Mensagens Duplicadas: Se dois consumidores processarem a mesma mensagem, elas serão duplicadas. Como resolver? Altere o Visibility Timeout para períodos mais longos.
- Fila com Alto Volume de Mensagens (Throughput Issues): Se você está usando filas FIFO, elas têm um limite de throughput. Para aumentar o throughput, você pode criar várias filas e distribuir a carga. Se necessário, altere para filas Standard que oferecem throughput mais alto. Você também pode aumentar a quantidade de instâncias de consumidores. 
- Mensagens perdidas: Ajuste o tempo de retenção e use a Dead Letter Queue (DLQ).
- Mensagens Não Processadas (Messages Not Being Processed): Altere o tipo de pooling a depender do cenário.


## :books: Referências
 - *https://docs.aws.amazon.com/sqs/*
<br />
<br />
