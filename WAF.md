<p align= "center">
  <img src="./Icons/Arch_AWS-WAF_64%405x.png" alt="WAF-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
WAF
    </h1>
</p>

O WAF (Web Application Firewall) é uma camada de segurança que protege aplicações web contra diversos tipos de ataques e ameaças. Ele age em camada 7 (aplicação) monitora, filtra e analisa o tráfego HTTP/HTTPS que entra em um aplicativo web para garantir que ataques maliciosos (como SQL Injection, Cross-Site Scripting (XSS), e ataques de negação de serviço (DDoS)) não cheguem até o servidor ou banco de dados.

## Integrações
- Amazon CloudFront: Filtra o tráfego malicioso perto do ponto de origem (bordas da rede), garantindo desempenho um pouco mais rápido que em outras integrações.
- Application Load Balancer (ALB): Protege o tráfego HTTP/HTTPS filtrando requisições antes de chegar aos servidores backend.
- API Gateway: Protege APIs públicas contra ataques como injeções SQL e XSS. Ideal para ambientes que expõem microserviços ou APIs RESTful para a internet.

## :books: Referências
 - *https://docs.aws.amazon.com/waf/*
<br />
<br />