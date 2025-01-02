<p align= "center">
  <img src="./Icons/Arch_AWS-Secrets-Manager_64%405x.png" alt="Secrets-Manager-icon" style="height:180px; width:180px;"/>
<br />
    <h2 align="center">
Secrets Manager
    </h2>
</p>
<br />
 O AWS Secrets Manager foi projetado para armazenar credenciais, como senhas de banco de dados, chaves de API e tokens de autenticação, com suporte a rotação automática, auditoria e acesso controlado.

 ## Features
 - Os segredos são criptografados automaticamente usando AWS KMS.
 - O Secrets Manager suporta a rotação automática de segredos
 - Integra-se com bancos de dados compatíveis, como Amazon RDS, Aurora, MySQL, PostgreSQL, SQL Server, entre outros, para atualizar automaticamente credenciais armazenadas no serviço.
 - Usando AWS Identity and Access Management (IAM), você pode controlar quem pode acessar ou gerenciar segredos.
 - Totalmente integrado ao AWS CloudTrail, o Secrets Manager registra todas as ações realizadas nos segredos, como criação, acesso, rotação e exclusão.
 
 ## Custos
 - Armazenamento de segredos: Cada segredo armazenado é cobrado mensalmente.
 - Uso de API: Há cobrança por solicitações adicionais de API (além de um limite gratuito inicial).

 # Diferenças com o SSM Parameter Store

| **Característica**                 | **AWS Secrets Manager**                   | **SSM Parameter Store**                      |
|------------------------------------|------------------------------------------|---------------------------------------------|
| **Rotação automática**             | Sim, integrada nativamente.              | Não nativa (requer funções Lambda).         |
| **Custos**                         | Maior, devido à funcionalidade avançada. | Menor, ideal para casos de uso simples.     |
| **Tipo de dados suportados**       | Strings, JSON e binários.                | Strings simples e criptografadas (`SecureString`). |
| **Gerenciamento de segredos**      | Avançado, com suporte a rotação, auditoria e integração. | Básico, com foco em parâmetros e segredos simples. |
| **Integração com bancos de dados** | Sim, com suporte a rotação automática.   | Não diretamente.                           |

## :books: Referências
 - *https://docs.aws.amazon.com/secretsmanager/*
<br />
<br />
