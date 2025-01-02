<p align= "center">
  <img src="./Icons/Arch_Amazon-Aurora_64%405x.png" alt="Aurora-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Aurora 
    </h1>
</p>

O Aurora é parte do serviço Amazon RDS e foi projetado para ser altamente escalável, rápido e resiliente. Ele é compatível com MySQL e Postgres. E pode ser até 5X mais rápido que o RDS MySQL e até 3X mais rápido que o RDS Postgres.<br>
O Aurora não é nativamente serverless mas ele oferece uma variante chamada Aurora Serverless

## Características
- Pode escalar de 10GB até 128 TB
- Pode ter até 15 read replicas
- FailOver instantâneo e automático
- Os dados são replicados automaticamente em seis cópias em três zonas de disponibilidade (AZs)
- Custa até 20% mais que o RDS.

## Aurora Serverless
- Não há necessidade de provisionar instâncias ou gerenciar a capacidade.
- Escala automaticamente para cima ou para baixo, dependendo da demanda (em unidades chamadas ACUs, Aurora Capacity Units).
- Ideal para cargas de trabalho com tráfego imprevisível ou intermitente.
- Você paga apenas pela capacidade consumida enquanto o banco está ativo.

## Quando usar cada um?
- Aurora Tradicional: Para cargas de trabalho previsíveis e de alta demanda, onde você precisa de controle sobre o desempenho. Um sistema ERP que precisa de performance consistente. 
- Aurora Serverless:  Para cargas de trabalho imprevisíveis, como um site que recebe tráfego esporádico ou um sistema de desenvolvimento/teste. Ou um e-commerce que tem picos de tráfego durante eventos promocionais.

## :books: Referências
 - *https://docs.aws.amazon.com/aurora/*
<br />
<br />