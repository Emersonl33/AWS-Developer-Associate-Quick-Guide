<p align= "center">
  <img src="./Icons/Arch_Amazon-DocumentDB_64%405x.png" alt="DynamoDB-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
DynamoDB
    </h1>
</p>

O Amazon DynamoDB é um serviço de banco de dados NoSQL totalmente gerenciado. projetado para fornecer alta performance, escalabilidade e confiabilidade para suas aplicações. Ele é amplamente utilizado em cenários que exigem grandes volumes de dados e baixa latência, como jogos online, aplicativos móveis, IoT (Internet das Coisas), entre outros.

## Modelos de capacidade
- Capacidade Provisionada: Você define a quantidade de leituras e gravações por segundo que precisa. Se o tráfego variar muito, pode ser necessário ajustar esses valores manualmente.
- Capacidade sob Demanda: O DynamoDB ajusta automaticamente a capacidade de leitura e gravação de acordo com o tráfego. Isso é útil para cargas de trabalho imprevisíveis ou quando não se sabe exatamente a demanda.

## DynamoDB Streams
- O DynamoDB Streams é um recurso do Amazon DynamoDB que captura e registra todas as alterações feitas em uma tabela, permitindo que você acompanhe as modificações (inserções, atualizações e exclusões) em tempo real. 
- Eventos do Stream: <br>
Insert: Quando um item é inserido na tabela.<br>
Modify: Quando um item é atualizado.<br>
Remove: Quando um item é excluído da tabela.
- Durabilidade: Os registros de stream são armazenados por 24 horas. Isso significa que, após esse período, os dados serão excluídos do stream automaticamente.
- Para acessar o conteúdo de um stream, você pode usar a API do DynamoDB Streams, que oferece operações como GetRecords, DescribeStream, ListStreams, entre outras, para gerenciar e processar os dados.

## DAX
- DAX (DynamoDB Accelerator) é um serviço de cache totalmente gerenciado que oferece desempenho de leitura em tempo real, com latência de leitura de apenas microsegundos.
- Cache de Leitura: O DAX armazena em cache as respostas de leitura do DynamoDB. Quando a aplicação faz uma leitura, o DAX primeiro verifica se a informação está no cache.
- Transparente: A integração do DAX com o DynamoDB é fácil, e você não precisa alterar seu código para usá-lo. A única modificação necessária é mudar o endpoint para o DAX, em vez de acessar diretamente o DynamoDB.

## Limitações do DAX
- Somente para Leituras: O DAX é útil apenas para acelerar leituras. Ele não acelera as operações de gravação, como inserções, atualizações ou exclusões, no DynamoDB.
- Cache Volátil: O DAX é um cache em memória, então ele pode ser evaporado quando o cluster é escalado ou reiniciado
- Custo: Embora o DAX ofereça uma redução significativa de latência, ele tem custos adicionais para manter os caches em memória

## Chaves
- Consiste apenas em uma única chave de partição. Quando você cria uma tabela com esse tipo de chave primária, o DynamoDB usa a chave de partição para distribuir os dados de maneira eficiente entre várias partições. <br>
Se você tem uma tabela de usuários, a chave de partição poderia ser o ID do usuário.
- Chave de Ordenação: Usada quando você precisa ordenar ou organizar dados dentro de uma partição. A chave de ordenação é sempre usada com a chave de partição para criar uma chave composta.

## Índices
- Tanto os Índices Globais Secundários (GSI) quanto os Índices Secundários Locais (LSI) são usados para melhorar o desempenho das consultas
| Característica                       | **GSI (Índice Global Secundário)**                   | **LSI (Índice Secundário Local)**               |
|--------------------------------------|------------------------------------------------------|--------------------------------------------------|
| **Chave de Partição**                | Pode ser diferente da chave de partição da tabela    | Deve ser a mesma chave de partição da tabela     |
| **Chave de Classificação**           | Pode ser diferente da chave de classificação da tabela | Deve ser a mesma chave de classificação da tabela|
| **Capacidade de Leitura/Gravação**   | Capacidade independente da tabela principal         | Compartilha a capacidade da tabela principal      |
| **Escalabilidade**                   | Escalável de forma independente                     | Não escalável independentemente                   |
| **Número Máximo de Índices**         | Ilimitado (dentro dos limites da conta)              | Máximo de 5 por tabela                           |
| **Consistência de Leitura**          | Eventual (ou forte, se configurado)                  | Consistente forte por padrão                     |
| **Uso Principal**                    | Flexibilidade em consultas e alto desempenho         | Consultas eficientes quando a chave de partição é constante|
| **Criação**                          | Pode ser criada depois da tabela                     | Só pode ser criada no momento da criação da tabela|



## Buscas
- Scan (Busca Completa): O Scan percorre toda a tabela, lendo todos os itens e verificando se atendem aos critérios fornecidos. Isso é menos eficiente, pois lê todos os dados da tabela, e não apenas um subconjunto.
- Query (Consulta): A Query é mais eficiente que o scan porque ela permite buscar dados usando a chave primária (ou um índice) para restringir os itens que precisam ser lidos. Você pode fornecer uma chave de partição e, opcionalmente, uma chave de ordenação para especificar quais itens deseja recuperar.
- Consulta com Índices Secundários: Índice Secundário Global (GSI) Se você tem um índice GSI com email como chave de partição e data de criação como chave de ordenação, pode buscar usuários com um email específico ou consultar todos os usuários em um intervalo de datas. <br>
Índice Secundário Local (LSI): Usado para consultas que mantêm a mesma chave de partição da tabela principal, mas permitem uma chave de ordenação diferente. O LSI oferece uma busca mais eficiente dentro de uma partição. Se sua tabela tem ID do usuário como chave de partição e ID do pedido como chave de ordenação, um LSI poderia ser criado usando data do pedido como chave de ordenação. Você poderia consultar todos os pedidos feitos por um usuário em uma data específica.

## WCUs e RCUs
| **Capacidade**                | **Unidade de Medição**                         | **Descrição**                                                                                     | **Exemplo**                                                                                              |
|-------------------------------|------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| **Write Capacity Units (WCU)** | 1 WCU = 1 gravação de até 1 KB por segundo     | Define o número de gravações que a tabela pode suportar por segundo. Uma gravação maior consome mais WCUs. | Se você gravar um item de 3 KB, você precisará de 3 WCUs.                                               |
| **Read Capacity Units (RCU)**  | 1 RCPU = 1 leitura de até 4 KB por segundo     | Define o número de leituras que a tabela pode suportar por segundo. Leitura eventualmente consistente consome menos RCUs. | Se você estiver lendo um item de 5 KB com leitura fortemente consistente, você precisará de 2 RCUs.      |


### **Cálculos de WCUs e RCUs**

| **Tipo de Capacidade**  | **Como calcular**                                             | **Exemplo**                                                                                             |
|-------------------------|---------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **WCU (Write Capacity Units)** | 1 WCU = 1 gravação de até 1 KB por segundo                    | Se você gravar um item de 3 KB, consumirá 3 WCUs.                                                        |
| **RCU (Read Capacity Units)**  | 1 RCPU = 1 leitura de até 4 KB por segundo (leitura fortemente consistente) | Se você estiver lendo um item de 5 KB com leitura fortemente consistente, precisará de 2 RCUs.          |
| **Leitura Eventualmente Consistente** | 1 RCPU = 2 leituras de até 4 KB por segundo                    | Para leituras de 1 KB com consistência eventual, 1 RCPU pode ler 2 itens de 1 KB por segundo.            |

### **Importância na Performance e Custo**

| **Capacidade**               | **Descrição**                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------|
| **Capacidade Provisionada**   | Você define manualmente o número de WCUs e RCUs para sua tabela. Se a capacidade provisionada for insuficiente, ocorrerá **throttling** (limitação de leitura/escrita). |
| **Capacidade Sob Demanda**    | O DynamoDB ajusta automaticamente a capacidade de WCUs e RCUs de acordo com a demanda, sem necessidade de ajuste manual.                                           |

## Tipos de Gravação
- PutItem: Grava ou substitui um item na tabela. Inserir ou substituir item completo.
- UpdateItem: Atualiza atributos específicos de um item sem substituir todo o item. Modificar atributos, como incrementar valores.
- DeleteItem: Exclui um item da tabela. Remover um item com base na chave primária
- BatchWriteItem: Realiza múltiplas operações de gravação (PutItem e DeleteItem) em um único pedido. Inserir ou excluir múltiplos itens em lote.
- TransactWriteItems: Executa várias operações de gravação em uma transação, garantindo atomicidade e consistência. Operações atômicas em uma ou várias tabelas.

## :books: Referências
 - *https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html*
<br />
<br />

