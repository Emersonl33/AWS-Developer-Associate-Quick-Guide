<p align= "center">
  <img src="./Icons/Arch_AWS-Certificate-Manager_64%405x.png" alt="ACM-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
ACM - AWS Certificate Manager
    </h1>
</p>

Facilita a criação, gerenciamento e implantação de certificados SSL/TLS para proteger sites e aplicativos na web. Esses certificados são usados para criptografar a comunicação entre os clientes (como navegadores ou dispositivos) e os servidores (como instâncias EC2, Elastic Load Balancers, etc.) 

## Principais Funções do AWS ACM:
- É possível emitir certificados públicos para domínios que você possui ou certificados privados para uso interno, como dentro de uma VPC (Virtual Private Cloud).
- O serviço permite gerenciar todos os certificados SSL/TLS em um único lugar. Você pode facilmente ver, renovar, revogar e implantar seus certificados.
- O ACM se integra de forma nativa com outros serviços da AWS, como Elastic Load Balancing (ELB), Amazon CloudFront, Amazon API Gateway, e AWS Elastic Beanstalk.

## Como funciona
- Você solicita um certificado no AWS ACM, seja para um domínio específico ou para múltiplos domínios (usando o tipo SAN - Subject Alternative Name).
- O ACM valida a propriedade do domínio, geralmente enviando um email de verificação ou pedindo uma verificação DNS.
- Após a emissão do certificado, você pode associá-lo automaticamente com serviços da AWS, como ELB, CloudFront ou API Gateway. Esses serviços podem gerenciar a instalação do certificado para você.
- O certificado pode ser usado para HTTPS, garantindo que as comunicações entre clientes e servidores sejam criptografadas.
- O ACM pode renovar automaticamente seus certificados antes que eles expirem. Isso reduz o risco de problemas de segurança causados por certificados expirados.

## Casos de uso
- Você possui um site hospedado em um Elastic Load Balancer (ELB) e deseja garantir que ele seja acessado via HTTPS (com criptografia SSL/TLS).

## Limitações 
- O ACM não oferece suporte para certificados de terceiros (por exemplo, se você já possui um certificado adquirido fora da AWS).
- Para a validação de domínio, você precisa ser capaz de modificar os registros DNS ou acessar os emails relacionados ao domínio para completar o processo de validação.

## :books: Referências
 - *https://docs.aws.amazon.com/acm/*
<br />
<br />