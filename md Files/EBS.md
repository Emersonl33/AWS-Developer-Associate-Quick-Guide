<p align= "center">
  <img src="./Icons/Arch_Amazon-Elastic-Block-Store_64%405x.png" alt="EBS-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
EBS
    </h1>
</p>

O EBS (Elastic Block Store) fornece armazenamento em bloco persistente para ser usado com instâncias do Amazon EC2. Em termos simples, o EBS é como um HD ou SSD virtual que você pode anexar às suas instâncias EC2 para armazenar dados de forma duradoura. Os dados armazenados em volumes EBS são persistentes, ou seja, permanecem disponíveis mesmo que a instância EC2 associada seja interrompida ou encerrada (dependendo do tipo de volume).
- Os volumes podem ter tamanhos que variam de 1 GiB a 64 TiB.
- Você cria um volume EBS em uma região e zona de disponibilidade específicas.
- Dentro da instância EC2, você pode formatar o volume, montar sistemas de arquivos e armazenar dados como faria em qualquer disco rígido.
- Você pode tirar snapshots do volume a qualquer momento, que podem ser usados para restaurar dados ou criar novos volumes.

## Tipos de volumes
- General Purpose SSD (gp3, gp2): Para uso geral com boa performance.
- Provisioned IOPS SSD (io2, io1): Para aplicativos críticos que exigem baixa latência e alta performance.
- Throughput Optimized HDD (st1): Para aplicativos que requerem alta taxa de transferência de dados, como processamento de grandes volumes de dados.
- Cold HDD (sc1): Para armazenamento de dados acessados com pouca frequência, com menor custo.

| **Tipo de Volume**            | **Descrição**                                                                                                                                               | **Casos de Uso**                                                                                                                                                  | **Desempenho**                                                                                     | **Custo**                          |
|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|-------------------------------------|
| **General Purpose SSD (gp3)** | SSD de uso geral com custo mais baixo e performance consistente. É o tipo padrão. Oferece **IOPS provisionados** de até 16.000 e throughput de 1.000 MB/s. | Aplicações de uso geral, como servidores web, sistemas de arquivos pequenos a médios e bancos de dados de latência moderada.                                      | 3.000 IOPS base com throughput ajustável. Pode ser configurado para até 16.000 IOPS e 1.000 MB/s.  | Custo eficiente para a maioria das aplicações. |
| **General Purpose SSD (gp2)** | SSD de uso geral, com performance que aumenta automaticamente com o tamanho do volume (até 16.000 IOPS). Está sendo gradualmente substituído pelo gp3.   | Casos de uso semelhantes ao gp3. Ideal para aplicações que não exigem alta personalização de performance.                                                         | 3 IOPS por GiB provisionado, com um limite máximo de 16.000 IOPS.                                  | Levemente mais caro que o gp3 para altas cargas de trabalho. |
| **Provisioned IOPS SSD (io2)** | SSD com IOPS provisionados, oferecendo alta durabilidade (99,999%). Ideal para cargas críticas.                                                       | Bancos de dados críticos, como Oracle e MySQL, sistemas OLTP e outras aplicações de baixa latência e alto throughput.                                             | Até 64.000 IOPS por volume e throughput de 1.000 MB/s.                                            | Custo mais alto devido à alta performance e durabilidade. |
| **Provisioned IOPS SSD (io1)** | Similar ao io2, mas com menor durabilidade. Está sendo gradualmente substituído pelo io2.                                                              | Casos semelhantes ao io2, mas com menos exigências de durabilidade.                                                                                               | Até 64.000 IOPS por volume.                                                                       | Levemente mais barato que o io2. |
| **Throughput Optimized HDD (st1)** | HDD otimizado para alta taxa de transferência de dados sequenciais.                                                                                | Processamento de big data, data warehouses, logs e armazenamento de dados de mídia, onde altas taxas de leitura/escrita são importantes.                         | Throughput sustentado de até 500 MB/s, com picos baseados no tamanho do volume.                   | Mais barato que SSDs, ideal para altas taxas de transferência. |
| **Cold HDD (sc1)**            | HDD de baixo custo otimizado para dados acessados com pouca frequência.                                                                                  | Arquivos frios, backups longos e armazenamento de dados raramente acessados.                                                                                      | Throughput sustentado de até 250 MB/s, com picos baseados no tamanho do volume.                   | O mais barato, ideal para dados raramente acessados. |
| **Magnetic (Standard)**       | Tipo mais antigo de armazenamento magnético. Está sendo descontinuado.                                                                                  | Apenas para cargas de trabalho legadas que ainda dependem de armazenamento magnético.                                                                             | Latência alta e performance inconsistente.                                                        | Geralmente mais caro que os tipos modernos de HDD. |


## Criptografia 
- A encriptação do Amazon EBS (Elastic Block Store) é projetada para proteger seus dados em repouso, em trânsito e durante backups com pouco ou nenhum impacto no desempenho. A AWS gerencia todo o processo de encriptação/desencriptação automaticamente.
- Quando você cria um snapshot de um volume encriptado, o snapshot também é encriptado automaticamente.

## Limitações
- Os volumes EBS estão vinculados a uma zona de disponibilidade específica. Para usá-los em outras zonas, é necessário copiar o volume (usando um snapshot) e recriá-lo na nova zona.
- Embora o volume seja persistente, ele só pode ser usado quando anexado a uma instância EC2.

## :books: Referências
 - *https://docs.aws.amazon.com/ebs/*
<br />
<br />