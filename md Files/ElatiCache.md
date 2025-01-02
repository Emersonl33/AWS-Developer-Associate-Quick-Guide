<p align= "center">
  <img src="./Icons/Arch_Amazon-ElastiCache_64%405x.png" alt="ElastiCache-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
ElastiCache
    </h1>
</p>

 O ElastiCache é um serviço gerenciado de cache na nuvem, que melhora o desempenho de aplicativos, reduzindo a carga nos bancos de dados e acelerando o tempo de resposta. Ele oferece duas opções principais: Redis e Memcached, para armazenar dados frequentemente acessados em memória, como sessões de usuário, resultados de consultas e filas de mensagens.

| **Característica**        | **Redis**                                   | **Memcached**                              |
|----------------------------|---------------------------------------------|--------------------------------------------|
| **Persistência de dados**  | Sim (opcional, em disco)                   | Não                                        |
| **Suporte a estruturas de dados** | Sim (listas, conjuntos, hashes, etc.) | Apenas pares chave-valor                   |
| **Clusterização**          | Sim (suporte nativo a sharding)            | Suporte básico                             |
| **Alta disponibilidade**   | Sim (replicação e failover automático)     | Não                                        |
| **Complexidade**           | Mais recursos, mas mais complexo de gerenciar | Mais simples e leve                       |

## TTL
- TTL podem ter um range de segundos, horas ou dias.
- É crucial saber configurar o TTL para o caso de uso adequado. Se vc colocar um TTL muito curto, isso pode ocasionar em uma sobracarga no banco, por outro lado, um ttl longo pode causar um cache muito grande e custoso.

## Casos de uso
- Em uma plataforma de e-commerce, ElastiCache pode ser usado para armazenar informações sobre os produtos mais vendidos. Sempre que um usuário acessar a página de um produto popular, o sistema verificará primeiro o cache (ElastiCache) para evitar uma consulta ao banco de dados, o que acelera o carregamento da página e reduz o custo de acesso ao banco.

## :books: Referências
 - *https://docs.aws.amazon.com/elasticache/*
<br />
<br />