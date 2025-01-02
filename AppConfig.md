<p align= "center">
  <img src="./Icons/Arch_AWS-AppConfig_64%405x.png" alt="AppConfig-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
AppConfig 
    </h1>
</p>

o AWS AppConfig facilita o gerenciamento centralizado e a implantação controlada de configurações em suas aplicações. É ideal para gerenciar configurações de aplicativos em ambientes de produção e desenvolvimento.<br>
O AppConfig permite que você atualize configurações sem necessidade de implantar novamente o código ou reiniciar o aplicativo.<br>
O seja, ele é tipo um controle remoto para suas configurações no app, permitindo mudar as coisas no backstage sem ninguém perceber e sem dar trabalho.

## Como funciona
- Criação de um "Application": Você define um "application" (aplicativo) no AppConfig. Isso pode ser um serviço ou sistema que usará as configurações.
- Criação de "Environments" (Ambientes): Crie ambientes como "desenvolvimento", "teste" e "produção", para diferentes versões e configurações.
- Definir "Configurations": Armazene configurações em um repositório, como o AWS Systems Manager Parameter Store ou o Amazon S3.
- Implantar Configurações: Implante as configurações para o seu aplicativo, controlando o processo de implantação para minimizar riscos.
- Monitoramento e Rollback: Acompanhe o desempenho da implantação e, se necessário, realize um rollback para uma configuração anterior.

## Caso de uso
- Imagina que você tem um app de música, tipo o Spotify, e quer oferecer uma promoção exclusiva para os usuários que ouvem bastante músicas de um gênero específico. Digamos que você quer oferecer um desconto para usuários que ouvem rock ou indie, mas só para um grupo pequeno de usuários por enquanto. Você quer ativar e desativar isso sem ficar mexendo no código do app toda hora. E sem precisar reimplantar o App.

## :books: Referências
 - *https://docs.aws.amazon.com/appconfig/*
<br />
<br />