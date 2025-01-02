<p align= "center">
  <img src="./Icons/Arch_AWS-Step-Functions_64%405x.png" alt="StepFunctions-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Step Functions
    </h1>
</p>

O AWS Step Functions é um serviço gerenciado que permite orquestrar fluxos de trabalho baseados em estados e ações, facilitando a execução de tarefas complexas. Com ele, você pode automatizar e coordenar processos que envolvem múltiplos serviços da AWS, como Lambda, SNS, SQS, DynamoDB, entre outros, criando aplicações baseadas em fluxos de trabalho visuais.

## Principais conceitos
- Máquina de Estados: A lógica do seu fluxo de trabalho é representada por uma máquina de estados, que define a sequência de estados e transições entre eles.
- Estados: Cada passo no processo. Um estado pode ser de diferentes tipos, como:<br>
Task: Executa uma ação, como invocar uma função Lambda.<br>
Choice: Realiza uma decisão condicional.<br>
Wait: Pausa a execução por um período específico.<br>
Parallel: Executa múltiplos ramos simultaneamente.<br>
Pass: Passa dados para o próximo estado sem realizar qualquer ação.<br>
Fail: Marca a execução como falhada.<br>
Succeed: Marca a execução como bem-sucedida.
- Transições: São as condições de transição entre os estados, determinando para qual estado o fluxo de trabalho irá se mover após a execução de cada tarefa.

## Máquinas de estado
- No AWS Step Functions, existem dois tipos principais de máquinas de estado: Standard e Express
- Standard Workflow: Quando o fluxo de trabalho precisa durar mais tempo (até 1 ano). Quando você está orquestrando processos complexos e de longo prazo, como processamento de dados ou integrações entre múltiplos serviços.
- Express Workflow: Quando o fluxo de trabalho precisa ser rápido e de baixo custo (com execução de até 5 minutos). Quando você precisa de alta escalabilidade e throughput (ex: processamento de eventos de sistemas distribuídos).

## Error Handling
- Quando um estado falha, você pode definir tentativas automáticas (com um intervalo entre elas) para que o fluxo de trabalho continue tentando executar a tarefa antes de capturar o erro.
- ErrorEquals: Define quais erros serão tratados (neste caso, qualquer erro - States.ALL).
- IntervalSeconds: Intervalo entre as tentativas (5 segundos).
- MaxAttempts: O número máximo de tentativas (3 tentativas).
- BackoffRate: A taxa de crescimento entre os intervalos de tentativas (dobrando a cada tentativa).
- Retry: Tenta novamente a execução de um estado em caso de falha (ideal para falhas temporárias).
- Catch: Captura erros e redireciona o fluxo para um estado específico de tratamento de erro.
- Fail: Marca a execução como falha, finalizando o fluxo.
- Choice: Permite decisões baseadas em condições, que podem ser usadas para lidar com falhas de maneira condicional.

## Estado Wait
- O estado Wait em AWS Step Functions é usado para pausar a execução do fluxo de trabalho por um período de tempo definido (em segundos) ou até uma data e hora específicas.
- Você pode usar Wait para aguardar eventos, como a conclusão de uma tarefa ou uma resposta de uma função Lambda.

## :books: Referências
 - *https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html*
<br />
<br />