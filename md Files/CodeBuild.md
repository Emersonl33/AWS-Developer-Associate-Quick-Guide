<p align= "center">
  <img src="./Icons/Arch_AWS-CodeBuild_64%405x.png" alt="CodeBuild-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
CodeBuild
    </h1>
</p>

O AWS CodeBuild é um serviço de Integração Contínua (CI) que automatiza o processo de compilação (build) do seu código. Ele pega o código-fonte, executa os testes e gera artefatos (como pacotes, binários ou imagens de containers)

## Estrutura de Arquivos do CodeBuild
- No código do arquivo buildspec.yml deverá conter as instruções para realizar o build. Este arquivo deve estar no diretório raiz(root directory) do seu código.
- Dependendo da linguagem ou framework que você está usando, pode haver arquivos específicos para gerenciar dependências.
- Node.js (npm): package.json e package-lock.json
- Java (Maven): pom.xml
- Python (pip): requirements.txt
- Docker: Dockerfile

## Cache
- Também é possível configurar o cache no buildspec.yml para armazenar dependências ou arquivos entre builds e acelerar a execução.

## :books: Referências
 - *https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html*
<br />
<br />