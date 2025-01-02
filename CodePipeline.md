<p align= "center">
  <img src="./Icons/Arch_AWS-CodePipeline_64%405x.png" alt="CodePipeline-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CodePipeline
    </h1>
</p>

O AWS CodePipeline é um grande integrador do seu processo de CI/CD, como uma linha de produção automatizada. Ele pega o código que você desenvolveu do seu repositório gtiHub, gtiLab etc... passa por etapas automáticas como build, testes e deploy, e coloca ele pronto para produção. Tudo sem você precisar fazer nada manualmente! É o processo de CI/CD na prática, onde cada mudança no código passa por uma sequência de etapas controladas, garantindo que tudo seja testado e entregue!🚀✅

## Fases do seu Pipeline
- Você pode definir várias fases (como Source, Build, Test, Deploy) e dentro de cada fase, você pode configurar ações específicas (como rodar um script, executar testes, fazer deploy, etc.).

# Ações personalizadas
- O CodePipeline oferece a possibilidade de adicionar ações personalizadas no pipeline, como executar scripts, integrar com sistemas externos ou ferramentas de terceiros, ou até mesmo realizar etapas que não estão nativamente disponíveis no serviço.

# Integrações
- Integra o processo de CI/CD end-to-end
- Conexão com CodeCommit, GitHub, S3.
- Integração com CodeBuild/CodeDeploy: Permite que o código seja implantado de maneira automatizada, com suporte a estratégias de deploy como Blue/Green e Canary, e a capacidade de fazer rollback automático em caso de falhas.
- Oferece integrações com o Amazon CloudWatch e Amazon SNS o que ajuda manter o controle sobre o andamento do pipeline e a receber alertas para intervir rapidamente, caso algo dê errado.
- O CodePipeline suporta múltiplas regiões AWS, permitindo que você orquestre o deploy de código em diferentes regiões de forma simultânea. Útil para empresas que operam em várias regiões e precisam garantir que o código seja implantado de forma consistente em todas as regiões.
- É possível usar o AWS CloudFormation para definir o pipeline como código. Assim, você pode versionar, automatizar e recriar pipelines facilmente em diferentes ambientes. Facilitando a automação e a repetibilidade do processo de criação e manutenção de pipelines, especialmente em ambientes de grandes empresas com múltiplas equipes.

# Rollbacks
- O CodePipeline pode automaticamente realizar rollback (voltar para uma versão anterior) caso uma etapa falhe, como no caso de um deploy que não funcione como esperado.

# Versionamento
- O CodePipeline oferece controle de versões para que você possa revisar e rastrear cada versão do código que passou por seu pipeline.

## :books: Referências
 - *https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html*
<br />
<br />
