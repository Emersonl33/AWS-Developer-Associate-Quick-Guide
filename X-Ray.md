<p align= "center">
  <img src="./Icons/Arch_AWS-X-Ray_64%405x.png" alt="X-Ray-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
X-Ray
    </h1>
</p>

Imagine que você tem uma aplicação complexa com várias partes conversando entre si (como APIs, bancos de dados, ou microservices). O X-Ray pega tudo isso, cria um mapa visual, e te mostra passo a passo o que está acontecendo, quanto tempo cada parte levou e onde estão os gargalos. Isso pode ser feito usando SDKs do X-Ray para diferentes linguagens (como Java, Node.js, Python, etc.) ou via AWS SDK para serviços integrados como Lambda, EC2, ECS, API Gateway, etc.


## Como integrar o X-RAY ao seu código
- A primeira etapa para usar o X-Ray é instrumentar seu código com o SDK do X-Ray. Isso envolve a inclusão de bibliotecas no seu código-fonte para que o X-Ray consiga coletar as informações de rastreamento.
- Configuração do Daemon: O Daemon do X-Ray deve ser executado em suas instâncias EC2 ou containers, para coletar e enviar os dados de rastreamento.
- Configuração do Console: Você pode acessar e analisar as informações diretamente no console do X-Ray, onde poderá ver as métricas, gráficos e rastreamentos de todas as requisições.

## Casos de Uso
- Diagnóstico de Erros: Se algo der errado em sua aplicação, você pode usar o X-Ray para rastrear o fluxo da requisição e entender onde o erro ocorreu.
- Otimização de Desempenho: O X-Ray pode identificar pontos lentos na aplicação, ajudando a otimizar o desempenho de cada serviço.
- Monitoramento de Aplicações Complexas: Ideal para aplicações distribuídas e baseadas em microserviços, o X-Ray facilita o monitoramento de serviços interdependentes.

## Limitações
- Por padrão, os rastreamentos são armazenados por até 30 dias.
- O uso do X-Ray pode gerar custos adicionais, então é importante monitorar a quantidade de dados sendo coletada e armazenada.

## :books: Referências
 - *https://docs.aws.amazon.com/xray/*
<br />
<br />