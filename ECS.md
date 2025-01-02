<p align= "center">
  <img src="./Icons/Arch_Amazon-Elastic-Container-Service_64%405x.png" alt="ECS-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
ECS
    </h1>
</p>

O Amazon Elastic Container Service (ECS) é um serviço da AWS que facilita a execução, o gerenciamento e a escalabilidade de contêineres na nuvem.

## Task Definitions
- Uma Task Definition (ou definição de tarefa) é uma especificação detalhada que descreve como um container deve ser executado no ECS. As task definitions definem os parâmetros de execução para uma ou mais containers, funcionando como um "plano de execução" para as tarefas.
- Executar contêineres no ECS: Toda tarefa ou serviço ECS precisa de uma definição de tarefa.
- Gerenciar configurações de contêineres: Permite que você defina as configurações de seus contêineres (imagem, variáveis de ambiente, limites de recursos, etc.).
- Automatizar implementações: Se você está automatizando a implementação de contêineres em um cluster ECS, as task definitions são essenciais.

```JSON
{
  "family": "my-task-family",
  "containerDefinitions": [
    {
      "name": "my-container",
      "image": "my-docker-image:latest",
      "cpu": 256,
      "memory": 512,
      "essential": true,
      "portMappings": [
        {
          "containerPort": 80,
          "hostPort": 80
        }
      ],
      "environment": [
        {
          "name": "MY_ENV_VAR",
          "value": "my-value"
        }
      ],
      "logConfiguration": {
        "logDriver": "awslogs",
        "options": {
          "awslogs-group": "/ecs/my-task",
          "awslogs-region": "us-west-2",
          "awslogs-stream-prefix": "my-container"
        }
      }
    }
  ]
}
```

## Volumes
- Host Volumes: Esses volumes são armazenados no próprio sistema de arquivos da instância EC2 que está executando a tarefa. São úteis quando você quer compartilhar dados entre múltiplos containers na mesma instância ou manter dados temporários.
- EFS Volumes (Amazon Elastic File System): Permite armazenar dados de forma persistente e acessível fora do ciclo de vida da instância. Os volumes EFS são ideais para dados que precisam ser compartilhados entre várias tarefas ou que precisam ser armazenados independentemente do ciclo de vida das tarefas. Funciona tanto para clusters baseados em EC2 quanto para Fargate, desde que a rede seja configurada corretamente.
- Ephemeral Storage: Armazenamento temporário específico do container em execução. O armazenamento efêmero é configurável em Fargate e pode ser configurado para tamanhos de até 200 GB.

## Task Placements
- Binpack: Coloca o máximo de tarefas possível em uma única instância para minimizar o número de instâncias usadas. Ideal para reduzir custos com instâncias EC2, pois maximiza o uso de recursos em cada instância. As tarefas são agrupadas nas instâncias com mais CPU e memória disponível, até que a capacidade seja preenchida.
- Spread: Distribui as tarefas de maneira uniforme entre instâncias, zonas de disponibilidade (Availability Zones) ou instâncias com base em atributos específicos. Ideal para aplicações sensíveis à disponibilidade ou que precisam de balanceamento de carga entre diferentes recursos
- Random: Coloca as tarefas aleatoriamente no cluster, distribuindo-as entre instâncias sem considerar a otimização de recursos.

## ECS Copilot
- AWS Copilot é uma ferramenta de linha de comando projetada para simplificar o processo de implantação e gerenciamento de aplicações conteinerizadas no Amazon Elastic Container Service (ECS) e AWS Fargate
- Melhores Práticas Integradas: O Copilot aplica automaticamente as melhores práticas para segurança, escalabilidade e monitoramento.
- Integração CI/CD: Facilita fluxos de trabalho de implantação contínua com opções de CI/CD integradas
- Usa arquivos YAML para definir configurações de serviço, tornando fácil personalizar implantações.

## Fargate
- O AWS Fargate é um serviço de computação sem servidor para containers, oferecido pela Amazon Web Services (AWS). Ele permite que você execute containers sem precisar gerenciar a infraestrutura subjacente, como servidores ou clusters de máquinas virtuais. Com o Fargate, você apenas define as configurações do seu container, como CPU e memória, e o serviço cuida do provisionamento, escalabilidade e gerenciamento da infraestrutura necessária para rodar os containers.
- Você paga apenas pelos recursos usados pelos containers, com cobrança baseada no tempo de execução e nos recursos consumidos.

## EKS
- Amazon EKS (Elastic Kubernetes Service) é um serviço gerenciado de orquestração de containers oferecido pela AWS, baseado no Kubernetes. O EKS permite que você execute, gerencie e escale aplicações em containers usando o Kubernetes sem a necessidade de instalar e operar sua própria infraestrutura de Kubernetes.
- O EKS usa o IAM (Identity and Access Management) da AWS para autenticar e autorizar os usuários do Kubernetes. Além disso, a comunicação entre os nós do Kubernetes e o plano de controle é criptografada
- O EKS facilita a implementação de pipelines de integração contínua e entrega contínua (CI/CD) para automatizar o ciclo de vida das aplicações, além de ser compatível com várias ferramentas de CI/CD, como Jenkins, GitLab, e CodePipeline.

## :books: Referências
 - *https://docs.aws.amazon.com/ecs/*
<br />
<br />