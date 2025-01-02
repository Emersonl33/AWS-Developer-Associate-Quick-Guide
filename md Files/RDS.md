<p align= "center">
  <img src="./Icons/Arch_Amazon-RDS_64%405x.png" alt="RDS-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
RDS
    </h1>
</p>

O Amazon RDS (Relational Database Service) é um serviço gerenciado da AWS que facilita a configuração, operação e escalabilidade de bancos de dados relacionais na nuvem. Ele elimina tarefas operacionais como instalação de software, provisionamento de hardware, backups, patching e recuperação de falhas. O RDS não é serverless, o que significa que você precisará provisionar instâncias.

## Suporte
- MySQL
- PostgreSQL
- MariaDB
- Oracle Database
- Microsoft SQL Server
- Amazon Aurora (otimizado pela AWS)

## RDS Custom for Oracle
- Dá a você acesso ao sistema operacional subjacente (host EC2), permitindo instalar extensões, ferramentas ou fazer configurações específicas.
- Suporta customizações, como patches ou configurações especiais do Oracle Database, que não seriam possíveis no RDS padrão.
- Usado, por exemplo, se você precisada de algumas funcionalidades do Oracle Enterprise Edition que necessita de permissões avançadas. Ou se você tem software legado que exige versões específicas ou configurações especiais do Oracle.

## Gerenciamento
- Backups automáticos e snapshots manuais.
- Atualizações automáticas de software.
- Escalabilidade vertical (mudar o tipo de instância) e horizontal (réplicas de leitura).

## Alta Disponibilidade
- Suporte a Multi-AZ
- Suporta também multi region mas isso gera um custo adicional elevado

## Read Replicas (Atenção pra esse ponto =))
- Read replicas são cópias assíncronas somente leitura do seu banco de dados usadas para mitigar problemas de performance em cenários onde existe uma carga muito grande de leituras no seu banco de dados principal.

## Distaser recovery
- Backups: O RDS faz backups automáticos do banco diariamente.E permite que você restaure o banco para um ponto no tempo específico, dentro do período de retenção configurado de até 35 dias.
- Snapshots Manuais: Você pode criar snapshots manuais a qualquer momento. Diferente dos backups automáticos, esses snapshots não expiram e podem ser usados para restaurar o banco quando necessário.
- Multi-AZ Deployment: O banco de dados principal é replicado automaticamente em outra zona de disponibilidade. Se a zona principal falhar, o RDS faz o failover automático para a réplica secundária.
- Read Replicas em Regiões Diferentes: Embora read replicas sejam para leitura, você pode promovê-las a banco de dados principal em caso de falha

## RDS Proxy
- Em situações de alto tráfego, sua aplicação pode abrir muitas conexões ao banco, sobrecarregando-o. O RDS Proxy gerencia um pool de conexões e as reutiliza, reduzindo a carga no banco de dados.
- Integra-se ao AWS Secrets Manager para gerenciar credenciais do banco de dados. Isso elimina a necessidade de armazenar senhas em sua aplicação.
- Funciona muito bem com funções Lambda que precisam se conectar a bancos de dados. Mas atenção!!! Se seu bancon estiver dentro de um sub net privada. Para sua função lambda ter acesso ao seu banco, ela precisará estar dentro da mesma VPC.

## :books: Referências
 - *https://docs.aws.amazon.com/rds/*
<br />
<br />
