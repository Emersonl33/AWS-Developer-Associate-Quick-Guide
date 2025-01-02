<p align= "center">
  <img src="./Icons/Arch_Amazon-Simple-Notification-Service_64%405x.png" alt="SNS-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
SNS
    </h1>
</p>


O Amazon SNS (Simple Notification Service) é um serviço de mensagens da AWS que permite que você envie notificações para diferentes tipos de destinatários, como usuários, sistemas, ou aplicações, de forma simples e eficiente. Assim como o SQS, o SNS também serve para desacoplar aplicações. O SNS é ideal quando você quer um modelo pub/sub (Publicar e Assinar), onde você envia uma mensagem a um tópico e vários assinantes podem consumir essa mensagem ao mesmo tempo em tempo real. Mas não tem nenhum recurso nativo para reprocessamento da mensagem em caso de falha.

## Componentes
- Publicador (Publisher): Você pode ser o publicador (quem envia as mensagens). Por exemplo, uma aplicação ou sistema que precisa avisar os usuários sobre algo, como uma nova atualização, um alerta ou promoções.
- Tópico (Topic): No SNS, as mensagens são enviadas para um tópico. Você pode pensar no tópico como uma lista de distribuição, ou seja, um grupo de pessoas ou sistemas para os quais você quer enviar uma mensagem.
- - Assinantes (Subscribers): Os assinantes são as pessoas ou sistemas que recebem a mensagem que você enviou para o tópico. Eles podem ser de diferentes tipos, como: <br>
SMS (mensagem de texto no celular)
E-mail (através de AWS SES)
HTTP(S) (enviar a mensagem para um servidor)
Lambda (executar uma função quando uma mensagem chega)
SQS (enviar para uma fila do Amazon SQS)

## Problemas Comuns
- Sobrecarga de mensagens e alta latência. Em vez de enviar muitas mensagens de uma vez, divida-as em lotes menores para garantir que o SNS possa processá-las com eficiência.
- Mensagens perdidas: Use SNS com SQS e configure uma DLQ no SQS.
- Tópicos sem assinantes ou assinantes não confirmados: Certifique-se de que todos os assinantes receberam e confirmaram a inscrição, especialmente em e-mails e SMS. No console do SNS, você pode verificar se o tópico tem assinantes ativos e se eles confirmaram sua inscrição.

## :books: Referências
 - *https://docs.aws.amazon.com/sns/*
<br />
<br />
