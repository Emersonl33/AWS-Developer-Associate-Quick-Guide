<p align= "center">
  <img src="./Icons/Arch_Amazon-Kinesis_64%405x.png" alt="Kinesis-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Kinesis
    </h1>
</p>

Esse serviço é bem útil e com certeza será cobrado. A palavra chave aqui é "Tempo-real". O exame costuma quebrar esse serviços em três, Kinesis Data Streams, Kinesis Data FireHose e Kinesis Data Analytics.  <br>
O AWS Kinesis é um serviço da Amazon que permite processar e analisar dados em tempo real. Ele é ideal para lidar com dados que chegam rapidamente e precisam ser processados e analisados imediatamente.<br>
Imagine que você tem muitos dados vindo de várias fontes ao mesmo tempo, como cliques em um site, fluxos de vídeos, dados de sensores de um dispositivo, ou transações bancárias. O Kinesis ajuda a coletar, processar e analisar esses dados de forma rápida e contínua.

## Kinesis Data Streams
- O Kinesis Data Streams é ideal para aplicativos que requerem processamento de dados em tempo real e para cenários como monitoramento de sistemas, análise de redes sociais, análise de dados de IoT (Internet das Coisas).

## Componentes do Kinesis Data Streams
- Streams: É a unidade básica no Kinesis, composta por shards. Cada shard pode processar uma quantidade de dados e fornecer uma taxa de transferência específica. Você pode aumentar ou diminuir a capacidade do stream adicionando ou removendo shards conforme necessário.
- Producers: São os aplicativos ou dispositivos que geram dados e os enviam para o Kinesis Data Streams. Esses produtores podem ser dispositivos IoT, aplicativos, ou qualquer sistema que gere dados de forma contínua.
- Consumers: São aplicativos ou processos que consomem os dados dos streams, processando e analisando as informações. O Kinesis permite que múltiplos consumidores leiam dados do mesmo stream simultaneamente, o que é útil para a análise paralela e escalabilidade.
- Shards: Cada shard tem uma taxa de entrada e saída de dados limitada. Se você precisar de maior capacidade, pode aumentar o número de shards no seu stream.

## Problemas comuns
- Latência Alta: Verifique a configuração do consumidor (ex.: Kinesis Client Library ou AWS Lambda) e a taxa de dados que está sendo processada. Aumentar o número de shards ou otimizar a lógica de processamento pode ajudar a reduzir a latência.
- Limitação de Taxa de Shards: Cada shard tem uma capacidade limitada (1 MB/s para gravação e 2 MB/s para leitura). Se a taxa de dados exceder essa capacidade, você precisará dividir os shards ou reconfigurar a aplicação para usar múltiplos shards para balancear a carga.
- Erros no Kinesis Data Streams API: A API pode retornar erros como ProvisionedThroughputExceededException se a taxa de requisições ultrapassar a capacidade. Aplique backoff exponencial ou ajuste os parâmetros da requisição para reduzir a quantidade de requisições simultâneas.

## KPL (Kinesis Producer Library)
- Uma biblioteca fornecida pela AWS para facilitar o envio de grandes volumes de dados para o Amazon Kinesis Data Streams de maneira eficiente. Ele abstrai a complexidade do envio de dados para o Kinesis, permitindo que os desenvolvedores se concentrem na lógica do aplicativo sem precisar se preocupar com detalhes de baixo nível.
- O KPL é ideal quando você precisa enviar grandes volumes de dados e deseja aproveitar as otimizações de desempenho e falha do Kinesis.

## Kinesis Fire Hose
- É como uma boca de **entrega** que pega os dados dos streams e os envia para outros serviços, como bancos de dados, S3, Redshift (para análise), ou até mesmo AWS OpenSearch.

## Casos de uso
- Monitoramento e alerta: Usar com o OpenSearch Service para armazenar e visualizar dados de logs de forma interativa.
- Análise em tempo real: Entregar dados de streaming diretamente para o Amazon Redshift para análise em tempo real.

## Kinesis Analytics
- Permite processar dados de streaming em tempo real, fornecendo insights instantâneos sobre os dados à medida que são ingeridos.

## Principais componenetes
- Kinesis Data Analytics para SQL: Permite criar aplicações que executam consultas SQL em dados de streaming em tempo real. Você pode analisar dados diretamente de Kinesis Data Streams ou Kinesis Data Firehose sem ter que escrever código complexo.
- Kinesis Data Analytics para Apache Flink: Para cenários mais complexos, o Apache Flink oferece um ambiente poderoso para processamento de fluxo e eventos. Você pode usar o Flink para operações como janelas de tempo, agregações complexas e análise de múltiplos streams simultaneamente

## Exemplos de uso
- Detecção de Fraude: Ao processar transações financeiras em tempo real, você pode usar Kinesis Data Analytics para detectar padrões de fraude, como transações duplicadas ou valores suspeitos, e gerar alertas instantâneos.
- Monitoramento de Logs: Você pode usar o Kinesis Data Analytics para analisar logs de aplicativos ou servidores em tempo real, identificar padrões ou anomalias e tomar ações em tempo real.

## :books: Referências
 - *https://docs.aws.amazon.com/kinesis/*
<br />
<br />

