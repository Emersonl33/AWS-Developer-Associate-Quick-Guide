<p align= "center">
  <img src="./Icons/Arch_AWS-Key-Management-Service_64%405x.png" alt="KMS-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
KMS
    </h1>
</p>

O AWS Key Management Service (KMS) é um serviço gerenciado de criptografia em repouso que facilita a criação, o gerenciamento, controle e rotação das chaves de criptografia em aplicações e serviços da AWS. 

## CMK
- Customer Master Keys (CMKs): CMKs são chaves mestras que você cria, controla e usa para criptografar e descriptografar dados. Elas podem ser:
- Gerenciadas pelo cliente: Criadas e controladas pelo usuário, com flexibilidade para definir políticas de acesso, rotação, e exclusão.
- Gerenciadas pela AWS: Criadas automaticamente para uso em serviços AWS, como S3 ou EBS.
- Provenientes de HSM: Criadas usando um AWS CloudHSM, garantindo maior controle e conformidade.
- A CMK nunca sai do KMS.
- Ela é usada para criptografar e descriptografar Data Keys, garantindo segurança no processo.

## Data Key
Imagina que você tem uma caixa super importante que quer manter segura. Essa caixa é tão grande que não dá pra ficar levando ela toda hora pro cofre principal (o KMS). Aí o que você faz? Pede ao KMS uma chave temporária só pra cuidar da sua caixa.
O KMS responde assim:
- "Aqui está uma cópia da chave em texto plano pra você usar agora e trancar sua caixa."
- "E aqui está outra cópia da chave, só que criptografada, pra guardar com a caixa caso precise destrancar no futuro."
Essa chave temporária é a Data Key. Ela é:
- Simples e eficiente: Tranca e destranca sua caixa rapidamente.
- Protegida pelo KMS: Se alguém encontrar a cópia criptografada, não consegue usá-la sem passar pelo KMS.
- No fundo, a Data Key é tipo uma chave de "uso diário", enquanto o KMS é o cofre que mantém a segurança de longo prazo. 😉
- Você pode gerar uma Data Key usando a operação ***GenerateDataKey*** do AWS KMS.
- O processo de usar uma Data Key para criptografar dados e protegê-la com uma KMS Key é chamado de Envelope Encryption

## Operações de criptografia
- *Encrypt*: Usa uma CMK para criptografar dados fornecidos pelo cliente.
- *Decrypt*: Descriptografa dados que foram protegidos com uma CMK.
- *GenerateDataKey*: Gera uma Data Key em plainText e uma versão criptografada. Ideal quando você precisa usar a chave imediatamente.
- *GenerateDataKeyWithoutPlaintext*: Retorna apenas a versão criptografada da Data Key, sem nunca expor a chave em um texto plano. Útil para cenários onde a geração e o uso da chave são separados e exige seguranca reforçada.
- *ReEncrypt*: Recriptografa dados que já foram criptografados, trocando a CMK usada.

## Criptografia Simétrica
- Chaves suportadas: Chaves simétricas (AES-256).
- Mesma chave usada para criptografar e descriptografar os dados.
- Ideal para a maioria dos casos de uso no AWS, como proteção de dados em volumes do EBS, objetos no S3 ou bancos de dados no RDS.

## Criptografia por Envelope
- Usa Data Keys (geradas pelo KMS) para criptografar os dados localmente.
- As Data Keys são protegidas por uma CMK simétrica ou assimétrica no KMS.
- Reduz a latência, pois os dados são criptografados localmente com a Data Key.

## Casos de uso das chaves do *GenerateDataKey* e *GenerateDataKeyWithoutPlaintext*
Use GenerateDataKey:
- Quando você precisa criptografar dados imediatamente e deseja simplicidade no fluxo de trabalho.
- Exemplo: Criptografar arquivos ou objetos no momento em que são gerados.
<br>
Use GenerateDataKeyWithoutPlaintext:
- Quando você quer gerar e armazenar chaves para uso posterior, sem risco de exposição.
- Exemplo: Configurar backups seguros onde as chaves criptografadas serão usadas mais tarde.

## Casos de uso Comuns do KMS
- Criptografia em repouso de volumes do EBS, objetos no S3, e bancos de dados usando padrão AES-256 com CMKs simétricas
- Geração de assinaturas digitais com chaves RSA ou ECDSA.
- Gerenciamento e rotação de chaves de criptografia

## Limitações
- Limite de solicitações: Varia de acordo com a região, mas geralmente é de 5.000 a 30.000 solicitações por segundo.
- Para criptografia simétrica (com uma CMK), o tamanho máximo de dados que podem ser criptografados em uma única operação é de 4 KB.
- As CMKs podem ser excluídas, mas você precisa aguardar entre 7 e 30 dias após a solicitação de exclusão para que a chave seja apagada permanentemente.
- O KMS é um serviço regional, o que significa que suas chaves estão disponíveis apenas dentro de uma região da AWS. Caso haja um problema com uma região, as chaves podem não estar acessíveis.
- Você não pode replicar suas chaves entre regiões automaticamente; precisaria criar e gerenciar chaves separadas em cada região.

## :books: Referências
 - *https://docs.aws.amazon.com/kms/*
<br />
<br />