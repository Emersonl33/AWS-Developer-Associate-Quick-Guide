<p align= "center">
  <img src="./Icons/Arch_Amazon-Athena_64%405x.png" alt="Athena-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Athena
    </h1>
</p>

O Athena é um serviço serverless de consulta sql que foi projetado para fazer consultas e análise de dados no S3. E essa é a informção mais útil para o exame =).

## Formatos compatíveis
- CSV, JSON, Parquet, ORC ou Avro.

##  Preço
- $5 USD por Terabyte Escaneado

## Casos de Uso comuns
- Logs: O athena é excelente para analisar logs de apps, servidores ou serviços<br>
<br>
Identificar o endereço IP com mais acessos ao servidor em logs do ELB.

```sql
SELECT client_ip, COUNT(*) AS total_requests
FROM elb_logs
GROUP BY client_ip
ORDER BY total_requests DESC
LIMIT 10;
```

- Data Lake e Big Data Analytics: Athena é frequentemente usado em arquiteturas de Data Lake para explorar grandes volumes de dados armazenados em formatos como Parquet e ORC.<br>
<br>
Analisar dados de vendas para insights de negócios, como produtos mais vendidos ou tendências sazonais.

```sql
SELECT produto, SUM(valor) AS total_vendas
FROM vendas
WHERE data BETWEEN '2024-01-01' AND '2024-12-31'
GROUP BY produto
ORDER BY total_vendas DESC;

```

## :books: Referências
 - *https://docs.aws.amazon.com/athena/*
<br />
<br />