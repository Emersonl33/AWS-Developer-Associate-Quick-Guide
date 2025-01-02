<p align= "center">
  <img src="./Icons/Arch_AWS-Lambda_64%405x.png" alt="Lambda-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Lambda λ
    </h1>
</p>

**Esse serviço é com certeza o mais cobrado no exame, por isso merece atenção especial e um estudo mais aprofundado.**
O AWS Lambda é um serviço de computação serverless, ou seja, que permite executar código sem *gerenciar servidores*, executando funções em resposta a eventos como uploads de arquivos, modificações em bancos de dados ou requisições HTTP.
O Lambda suporta várias linguagens de programação, como Python, Node.js, Java, C#, Go, Ruby, entre outras...
Você paga pelo tempo de execução do código e pela quantidade de recursos computacionais (memória) que ele utiliza

## Estrutura
- Função Lambda: O código executável.
- Evento: A origem do acionamento da função (ex: um arquivo S3).
- Handler: O método que é executado (***Atenção pra esse ponto!***) Sempre que você for acessar bancos de dados usando lambda se atente para deixar as Strings de autenticação do banco **FORA** do método handler! Isso vai aumentar a performance do seu acesso e execução da função
- Configuração: Tempo limite (***Atenção pra esse ponto!***) As funções lambda têm um tempo de execução máximo de 15 minutos, sendo assim, o uso do Lambda não é adequado para cargas de trabalho que ultrapassem esse tempo.
- Configuração: Memória e CPU (***Atenção pra esse ponto!***) O poder de processamento da CPU do Lambda está diretamente ligado à memória. Quando voê aumenta sua capacidade de memória, sua CPU é automaticamente redimensionada proporcionalmente à quantidade de memória que você aumentou.
- Contexto: Informações sobre a execução.
- IAM Role: Permissões necessárias para acessar outros recursos.

## Invocação Síncrona: 
- O cliente espera pela resposta da função Lambda. O AWS Lambda processa a requisição e retorna o resultado imediatamente para o cliente após a execução da função.
- Usado para invocações em que você precisa da resposta imediatamente, como em APIs ou chamadas diretas de uma aplicação.
- InvocationType='RequestResponse'

## Invocação Assíncrona:
- Na invocação assíncrona, o cliente envia uma requisição para a função Lambda, mas não espera pela resposta. O AWS Lambda coloca o evento em uma fila e a função é invocada assim que possível. O Lambda não retorna a resposta ao cliente.
- Podem ser usados para processamento de arquivos após o upload para o S3 ou processamento de eventos do SNS, por exemplo.
- A execução da função não é limitada a 15 minutos, mas eventos não processados ficam na fila por até 7 dias.
- InvocationType='Event'

## Camadas
- Camadas (Layers) São uma maneira de empacotar e compartilhar código, bibliotecas e dependências que podem ser reutilizados em várias funções Lambda. Em vez de empacotar todas as dependências dentro do código da função, você pode usar camadas para compartilhar essas dependências entre diferentes funções.
- Cada função Lambda pode usar até 5 camadas por vez, incluindo a camada padrão (o código da própria função Lambda)
- O tamanho máximo de uma camada é 50 MB quando compactada. No entanto, é possível usar até 250 MB de dados descompactados.
- Você pode criar camadas e compartilhá-las com outras contas AWS ou regiões.
- Além das bibliotecas de código, você também pode usar camadas para fornecer arquivos específicos do sistema operacional ou scripts de configuração necessários para sua função.

## Versões
- Uma versão de função Lambda é um snapshot imutável do código e da configuração de uma função no momento em que ela é criada
- Uma vez publicada, a versão não pode ser alterada
- Cada versão tem um número único
- Você pode referenciar diretamente uma versão específica de uma função, usando o número da versão (ex.: *arn:aws:lambda:region:account-id:function:function-name:1*).
- Versão $LATEST (***Atenção pra esse ponto!***): O $LATEST é a versão não publicada e em constante atualização. Ele sempre aponta para a versão mais recente do código da função Lambda, mas não é imutável como outras versões publicadas. 
A versão $LATEST não deve ser utilizada em ambientes de produção.

## Aliases
- Um alias é uma referência estável a uma **versão** de uma função Lambda. Enquanto a versão é imutável, o alias permite que você apontar para diferentes versões de uma função.
- Um alias não pode apontar para outro alias Atribuição de Percentual de Tráfego(***Atenção pra esse ponto!***)
- Um alias tem um nome estável, como prod, dev, test, etc., e pode apontar para qualquer versão específica de uma função Lambda.
- Você pode alterar o alias para apontar para diferentes versões, sem alterar o código da função.
- Atribuição de Percentual de Tráfego(***Atenção pra esse ponto!***): Você pode configurar aliases para distribuir o tráfego entre diferentes versões de forma gradual (usado, por exemplo, para deploys canary).

## Exemplo prático
- Suponha que você tenha uma função Lambda com o código em sua versão 1. Se você fizer alterações no código e publicar uma nova versão (versão 2), a versão 1 será preservada e não será afetada.
- Você pode criar um alias chamado prod que aponte para a versão 1 da função. Quando você publicar a versão 2, pode alterar o alias prod para apontar para a nova versão. Assim, o ambiente de produção será atualizado sem afetar outras funções ou versões.

## Execução agendada
- Lambda pode ser invocado em horários específicos ou com base em uma agenda usando Amazon CloudWatch Events.

## Diretório /tmp
- (***Atenção pra esse ponto!***) O diretório /tmp pode ser usado como Cache temporário para cálculos ou estados de execução.
- Capacidade de armazenamento de 512 MB pode ser um limitador para funções que precisam manipular grandes quantidades de dados.
- Como o conteúdo do diretório /tmp é removido após a execução, ele não é adequado para persistir dados entre diferentes invocações de funções Lambda.

## Lambda em contêiners
- Desde 2020, o Lambda permite que você empacote suas funções em containers Docker e execute-os no ambiente Lambda. Isso significa que você não precisa se preocupar com a infraestrutura do contêiner, apenas com o código dentro do contêiner.
- ideal para funções de curta duração. Se sua aplicação pode ser dividida em tarefas discretas e pequenas (por exemplo, processar uploads de arquivos, responder a requisições HTTP em APIs, ou processar eventos de fila), o Lambda pode ser uma solução muito eficaz.

## Execução no ambiente VPC
- Sempre que você precisar acessar recursos que estão limitadas a uma VPC ou sub rede privada, é necessário colocar sua função Lambda dentro dessa VPC
