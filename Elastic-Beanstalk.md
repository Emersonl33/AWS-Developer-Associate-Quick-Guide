<p align= "center">
  <img src="./Icons/Arch_AWS-Elastic-Beanstalk_64%405x.png" alt="ElasticBeanStalk-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Elastic BeanStalk
    </h1>
</p>

Esse com certeza é mais um tópico super importante para o Exame, e um dos meus serviços favoritos da AWS. <br>
O AWS Elastic Beanstalk é uma maneira fácil de subir e gerenciar aplicações na nuvem sem precisar se preocupar com a infraestrutura. Em vez de configurar servidores, redes e bancos de dados manualmente, você só precisa focar no seu código, e o Beanstalk cuida do resto. <br>
**Imagine o seguinte:** <br>
Você tem uma aplicação web, tipo um site ou uma API, e quer rodá-la na nuvem. Em vez de gastar tempo configurando servidores e instalando coisas, você só faz o upload do código e diz para o Elastic Beanstalk em que linguagem ele foi feito (Python, Java, Node.js, Ruby, etc). Ele automaticamente configura o ambiente para você, escala a aplicação conforme a necessidade e até monitora o desempenho.

## Tipos de Deploy
- All at Once (Tudo de uma vez):  É a opção mais rápida, já que todas as instâncias são atualizadas simultaneamente. Pode causar indisponibilidade durante o processo, pois não há tempo de transição ou rollback se algo der errado.
- Rolling Deployment (Implantação em lote): Atualiza as instâncias em pequenos grupos (batches) de uma vez. Ou seja, um lote de instâncias é atualizado, enquanto o restante continua rodando a versão antiga. Durante o deployment, pode haver versões diferentes da aplicação rodando em diferentes servidores.
- Rolling with Additional Batch (Rolling com lote adicional): Cria uma nova instância (ou mais, dependendo da configuração) antes de iniciar o processo de atualização. Isso garante que o número original de instâncias esteja sempre disponível, mesmo durante a atualização. Mantém a capacidade de servidores enquanto atualiza. É uma opção segura para grandes aplicações que não podem perder desempenho durante a atualização. Pode aumentar os custos momentaneamente, já que você estará rodando instâncias extras.
- Immutable Deployment (Implantação imutável): Você envia uma nova versão da aplicação, o Elastic Beanstalk prepara novas instâncias, testa e, se tudo correr bem, coloca as novas instâncias no ar, tudo isso sem que os usuários percebam ou experimentem qualquer falha. É a maneira mais segura, já que se algo der errado, o rollback é simples e rápido. É mais caro, pois envolve a criação de um novo conjunto de instâncias temporárias. Também é um processo mais lento.
- Blue/Green Deployment (Implantação Azul/Verde): Mantém dois ambientes separados: um ambiente "azul" (produção atual) e um ambiente "verde" (com a nova versão da aplicação). Depois de testar o ambiente verde, você faz um switch para direcionar o tráfego para ele. Pode ser mais complexo de gerenciar e mais caro, pois requer dois ambientes rodando ao mesmo tempo.

## LifeCycle Policy
- A Lifecycle Policy no AWS Elastic Beanstalk ajuda a gerenciar automaticamente as versões de aplicação que você carrega na sua conta, permitindo controlar o número de versões armazenadas e evitar que o repositório se encha de versões antigas. Essa política é essencial para evitar que o seu ambiente consuma muito armazenamento desnecessariamente, já que cada versão da aplicação é armazenada no Amazon S3 e pode ocupar bastante espaço ao longo do tempo.
- As versões excluídas pela política de ciclo de vida não podem ser recuperadas.

## Extensions
- Servem basicamente para customização: Instalar bibliotecas, configurar serviços, ou ajustar parâmetros do servidor para necessidades específicas da aplicação.
- Essas extensões são geralmente configuradas em arquivos com o sufixo .config e são colocadas na pasta .ebextensions dentro do seu diretório de aplicação.
- Pode ser usado para Ambientes de teste e produção diferentes

## :books: Referências
 - *https://docs.aws.amazon.com/elastic-beanstalk/*
<br />
<br />
