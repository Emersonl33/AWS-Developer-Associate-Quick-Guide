<p align= "center">
  <img src=".Icons/Arch_Amazon-CloudFront_64%405x.png" alt="Cloud-Front-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Cloud Front
    </h1>
</p>

O Cloud Front é um serviço de entrega de conteúdo pela rede, como sites estáticos e dinâmicos, vídeos, APIs, entre outros, de forma rápida e segura para usuários ao redor do mundo. O objetivo do CloudFront é melhorar a performance, reduzir a latência e fornecer uma experiência de usuário mais rápida, independentemente de onde o usuário esteja.<br>
O CloudFront tem uma rede de pontos de presença espalhados por várias regiões ao redor do mundo, conhecidos como Edge Locations. Esses pontos são servidores que armazenam em cache o conteúdo estático da sua aplicação (como imagens, vídeos, páginas HTML, etc.).

## Como funciona
- Quando um usuário faz uma requisição para o seu site ou aplicação, o CloudFront tenta entregar o conteúdo a partir do ponto de presença mais próximo da sua localização, reduzindo a distância que os dados precisam percorrer e, consequentemente, melhorando a velocidade de carregamento.
- Cache Dinâmico: Para conteúdos dinâmicos que não podem ser armazenados em cache (como resultados de consultas em tempo real), o CloudFront pode ser configurado para encaminhar as requisições diretamente para o origem do conteúdo, como um servidor de origem ou um bucket S3, sem perder a agilidade da rede de entrega.

## Caso de uso
- Imagine que você tem conteúdo estático de um site de e-commerce com imagens, arquivos CSS e HTML que são acessados por usuários de várias partes do mundo. Ao usar o CloudFront: Você configura uma distribuição, apontando para o S3 bucket que armazena esses dados.Se o tráfego crescer rapidamente durante uma promoção, o CloudFront pode lidar com o aumento de demanda sem que você precise alterar a infraestrutura.

## Geo Restriction
- Você pode configurar o CloudFront para permitir o acesso ao conteúdo apenas de determinados países ou regiões. Isso pode ser útil, por exemplo, se você deseja restringir o acesso a um site apenas a usuários de um país específico ou a um grupo de países.
- O CloudFront usa o endereço IP do usuário para determinar a localização geográfica. Isso pode não ser 100% preciso, já que usuários podem usar VPNs ou proxies para mascarar sua localização real.
- O serviço de geo-restrição não oferece granularidade por região dentro de um país (por exemplo, não é possível bloquear um estado específico dentro de um país).

## :books: Referências
 - *https://docs.aws.amazon.com/cloudfront/*
<br />
<br />