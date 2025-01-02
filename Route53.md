<p align= "center">
  <img src="./Icons/Arch_Amazon-Route-53_64%405x.png" alt="Route-53-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Route 53
    </h1>
</p>

O Amazon Route 53 é um serviço de DNS (Domain Name System). Ele permite que você gerencie os nomes de domínio e as configurações de DNS. Quando um usuário digita um endereço de site no navegador, o Route 53 resolve esse nome de domínio em um endereço IP. Isso é feito por meio de uma consulta DNS, onde o serviço localiza os servidores responsáveis por esse domínio e direciona o tráfego corretamente. Você pode registrar e gerenciar domínios diretamente no Route 53, sem precisar de um provedor externo. Isso inclui a compra de novos domínios, a configuração de registros DNS para esses domínios e a renovação do registro.

## Tipos de roteamento de tráfego
- Roteamento simples: Mapeamento direto de domínios para endereços IP ou instâncias de recursos.
- Roteamento baseado em latência: Direciona os usuários para o recurso mais próximo de sua localização, melhorando a performance.
- Roteamento geográfico: Direciona os usuários com base na sua localização geográfica.
- Roteamento ponderado: Permite distribuir o tráfego entre diferentes recursos de acordo com uma porcentagem especificada.
- Failover: Redireciona automaticamente o tráfego para um recurso alternativo se o recurso principal falhar.

## Health checks
- O Route 53 pode ser configurado para monitorar a saúde dos recursos (como servidores web, instâncias EC2, etc.). Caso um recurso falhe, ele pode redirecionar o tráfego automaticamente para outro recurso saudável, garantindo alta disponibilidade.

## CNAME
- Um CNAME é um registro de DNS que mapeia um nome de domínio para outro nome de domínio. Quando alguém acessa o domínio apontado pelo CNAME, a consulta DNS será resolvida para o endereço do domínio alvo.
- Exemplo: www.exemplo.com → meusite.exemplo.com
- Quando alguém acessar www.exemplo.com, o DNS vai resolver para meusite.exemplo.com.
- só pode ser usado em Subdomínios (não pode ser usado no domínio raiz).

## Alias 
- Um Alias é um tipo especial de registro DNS que é exclusivo do Amazon Route 53. Ele mapeia um nome de domínio para um recurso da AWS, como um balanço de carga (ELB), CloudFront, S3 bucket, ou outros recursos da AWS, sem precisar de um endereço IP explícito.
- Com um Alias, você pode apontar diretamente para serviços como Elastic Load Balancer (ELB), Amazon CloudFront, S3, e Route 53 com um domínio raiz ou subdomínio. Isso não é possível com CNAME.
- Pode ser usado para subdomínios e domínio raiz
- Exemplo: exemplo.com → meusite.s3-website-us-east-1.amazonaws.com
- Aqui, você pode apontar diretamente para o S3 bucket de hospedagem de site estático, sem precisar de um endereço IP ou nome de domínio intermediário.

## TTL (Time-To-Live)
- TTL (Time to Live) é um parâmetro associado a registros DNS que especifica por quanto tempo, em segundos, um registro pode ser armazenado em cache por servidores DNS e resolvers antes de ser considerado "expirado"
- Um TTL menor significa que os registros expirarão mais rapidamente e, portanto, serão consultados com mais frequência. Um TTL maior significa que os registros permanecerão em cache por mais tempo, reduzindo o número de consultas ao servidor DNS.
- TTL Baixo: Pode levar a mais consultas ao servidor DNS, o que pode aumentar a latência e os custos de consulta.
- TTL Alto: Pode reduzir o número de consultas e melhorar o desempenho, mas pode causar atraso na propagação de alterações, pois as mudanças nos registros só serão refletidas após a expiração do TTL.

## :books: Referências
 - *https://docs.aws.amazon.com/route53/*
<br />
<br />