<p align= "center">
  <img src="./Icons/Arch_Amazon-MemoryDB-for-Redis_64%405x.png" alt="MemoryDB-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
MemoryDB 
    </h1>
</p>

MemoryDB é um DataBase de chave-valor baseado no Redis. Todo o banco de dados é armazenado na memória RAM, proporcionando desempenho ultrarrápido para leituras e gravações. Diferentemente de outros bancos de dados apenas em memória, o MemoryDB oferece persistência automática, gravando dados em disco continuamente para garantir a durabilidade e a recuperação em caso de falhas. Ele é um serviço gerenciado que requer que você defina o tamanho e a configuração do cluster, como número de nós e shards, para suportar sua aplicação

## Casos de uso comuns
- Sessões de usuário: Gerenciamento de sessões em tempo real para aplicativos da web.
- Cache em tempo real: Armazenar respostas frequentes para diminuir a carga em bancos de dados primários.
- Filas de mensagens: Implementar filas de mensagens com baixa latência.

## Custo
- A cobrança é feita com base no tipo e no número de instâncias (nós) em execução, bem como no uso de armazenamento de backup, em vez de ser puramente baseado no consumo real de recursos.

## :books: Referências
 - *https://docs.aws.amazon.com/memorydb/*
<br />
<br />