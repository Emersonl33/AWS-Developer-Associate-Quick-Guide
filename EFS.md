<p align= "center">
  <img src="./Icons/Arch_Amazon-EFS_64%405x.png" alt="EFS-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
EFS
    </h1>
</p>

O AWS EFS (Amazon Elastic File System) é um serviço de armazenamento de arquivos na nuvem oferecido pela Amazon Web Services. Ele funciona como um disco compartilhado que pode ser acessado simultaneamente por vários servidores ou computadores, semelhante a um drive de rede.

- EFS é como um "pendrive na nuvem", mas que várias pessoas (ou servidores) podem usar ao mesmo tempo.
- É elástico: ele cresce e diminui automaticamente conforme você adiciona ou remove arquivos, sem precisar se preocupar com espaço.
- É muito útil para cenários onde várias máquinas precisam acessar os mesmos dados ao mesmo tempo, como em aplicativos que rodam em vários servidores.

## Compatibilidade
- Atualmente o Amazon EFS (Elastic File System) é compatível apenas com sistemas baseados em Linux. Isso ocorre porque ele utiliza o protocolo NFS (Network File System), que é nativamente suportado pelo Linux.

## Custo
- O custo do EFS é baseado no uso real de armazenamento (quanto você armazena), e não em provisionamento de capacidade, o que torna o custo mais flexível.
- Você paga por GB armazenado, e o custo varia dependendo da região e da classe de armazenamento.

## Usos Comuns
- Aplicações Web Escaláveis: Que requerem vários servidores acessando o mesmo conjunto de arquivos de conteúdo.
- Armazenamento para Contêineres: Usado em ambientes que exigem compartilhamento de dados entre contêineres (como o Kubernetes).

## Tipos de armazenamentos

| Tipo de Armazenamento       | Custo         | Desempenho             | Uso Ideal                                      |
|-----------------------------|---------------|------------------------|------------------------------------------------|
| **Padrão (Standard)**        | Mais caro     | Consistente e alto     | Aplicações com acesso frequente e alto desempenho, como servidores de arquivos e aplicações web escaláveis. |
| **Acesso Infrequente (IA)**  | Mais barato   | Menor desempenho       | Dados acessados de forma esporádica, como backups e arquivos antigos. Ideal para reduzir custos em dados pouco acessados. |

- Além das classes de armazenamento, o EFS também oferece modos de desempenho que influenciam a velocidade e a capacidade de I/O:<br>
Padrão: Ideal para a maioria dos aplicativos. Ele oferece um bom equilíbrio entre desempenho e custo para cargas de trabalho comuns.<br>
Max I/O: Para cargas de trabalho que exigem maior taxa de transferência e maior paralelismo, com um pouco mais de latência. Esse modo é mais adequado para aplicações de big data e grandes volumes de dados.

## :books: Referências
 - *https://docs.aws.amazon.com/efs/*
<br />
<br />