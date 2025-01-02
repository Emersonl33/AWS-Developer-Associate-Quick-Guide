<p align= "center">
  <img src="./Icons/Arch_Amazon-API-Gateway_64%405x.png" alt="API-Gateway-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
API Gateway
    </h1>
</p>

Esse é um dos tópicos mais importantes para a prova que com certeza cobrará a maioria dos conceitos aqui.<br>
O API Gateway facilita a criação, o gerenciamento e a exposição de APIs para suas aplicações. Em outras palavras, ele serve como uma porta de entrada para suas APIs, permitindo que você controle o acesso e a forma como os dados circulam entre seus usuários/clientes e os backends (serviços, bancos de dados, microservices, etc.).<br>
Pensa nele como um porteiro digital: ele recebe as requisições dos usuários, valida, faz roteamento, aplica regras de segurança e, finalmente, repassa para o serviço correto fazer o trabalho. Ele também pode fazer coisas como limitar o tráfego, monitorar o uso e tratar falhas. 

## APIs suportadas
- REST APIs:  As REST APIs (Representational State Transfer) são o tipo mais comum de API na web. Elas seguem o padrão de arquitetura REST, onde as requisições HTTP (GET, POST, PUT, DELETE, etc.) são usadas para interagir com recursos em um servidor. Ideal para serviços web tradicionais. Pode ser integrada a backends, como AWS Lambda, EC2, S3, ou até mesmo outros serviços externos. 
- WebSocket APIs: As WebSocket APIs são usadas para criar conexões bidirecionais entre o cliente e o servidor. Isso permite que o servidor envie dados ao cliente em tempo real sem que o cliente precise fazer uma requisição constantemente. Ideal para aplicações que exigem comunicação em tempo real, como chats, jogos online, ou notificações push.

## Principais componentes:
- Stages: O stage é usado para organizar e separar suas apis, vc pode criar múltiplos ambientes, como dev, test e prod.
- Método: Cada método é uma ação HTTP (como GET, POST, PUT, DELETE) que pode ser aplicada a um recurso. Por exemplo, em /users, você pode ter o método GET para obter a lista de usuários e POST para criar um novo usuário.
- Deployment: O deployment é o processo de publicar a versão da API em um stage. Quando você faz mudanças na API, precisa criar um novo deployment para tornar essas mudanças ativas.

## Variáveis de estágio
- As variáveis de estágio são valores associados a um estágio específico da sua API (como dev, staging, prod). Elas são usadas para armazenar informações que podem ser alteradas de acordo com o ambiente, como URLs de serviços, credenciais, parâmetros de configuração, entre outros. Essas variáveis permitem que você configure sua API de forma flexível, sem necessidade de mudanças no código.
- Você pode usar variáveis para alterar o endereço do backend entre ambientes. Por exemplo, em um estágio dev, você pode usar o URL de um banco de dados de desenvolvimento, enquanto em produção usa o de um banco de dados real.
- Você pode configurar diferentes chaves de API ou tokens de autenticação para diferentes estágios.

## Autorizadores
- Autorizador Cognito (Cognito Authorizer): O Cognito Authorizer usa o serviço Amazon Cognito para autenticar usuários. O Cognito fornece uma maneira fácil de gerenciar usuários e suas credenciais (como tokens JWT, OAuth2 ou SAML).
- Autorizador Lambda: Quando uma requisição é recebida, o API Gateway chama a função Lambda definida para o autorizador, passando os detalhes da requisição, como headers, parâmetros de query ou corpo. A função Lambda pode então processar esses dados, realizar a autenticação (como verificar um token JWT, API Key ou até mesmo consultar um banco de dados) e retornar uma resposta dizendo se a requisição é autorizada ou não.
- Se a requisição não for autorizada, o API Gateway retorna um erro, como 401 Unauthorized.

## Integração com o Lambda
- Quando um cliente faz uma requisição para a API, o API Gateway pode ser configurado para enviar essa requisição diretamente para uma função Lambda. A função Lambda processa a requisição, executa a lógica desejada (por exemplo, buscar dados em um banco de dados, realizar cálculos, etc.) e retorna uma resposta ao API Gateway, que por sua vez retorna a resposta para o cliente.
- O API Gateway precisa de permissões para invocar a função Lambda. Para isso, você deve criar uma role IAM que permite ao API Gateway invocar a função Lambda e associá-la ao API Gateway. Isso é feito automaticamente se você usar o console do API Gateway para configurar a integração.
- Depois de configurar, você pode testar a API diretamente no console do API Gateway. Ele enviará a requisição para a função Lambda e mostrará a resposta.

## Cache
- O cache armazena os resultados das respostas em memória, e se uma solicitação subsequente para o mesmo recurso for feita, o API Gateway pode retornar a resposta diretamente do cache em vez de executar novamente toda a lógica da API, como chamadas a bancos de dados ou outros serviços.
- Você pode configurar a duração do cache (TTL - Time to Live) para controlar quanto tempo os dados devem ser armazenados antes de expirar e fazer uma nova solicitação ao backend.



## :books: Referências
 - *https://docs.aws.amazon.com/apigateway/*
<br />
<br />
