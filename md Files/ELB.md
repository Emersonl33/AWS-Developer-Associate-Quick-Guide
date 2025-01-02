<p align= "center">
  <img src="./Icons/Arch_Elastic-Load-Balancing_64%405x.png" alt="Cloud-Front-icon" style="height:180px; width:180px;"/>
<br />
    <h1 align="center">
Elastic Load Balancer
    </h1>
</p>

O Elastic Load Balancer (ELB) é um serviço que distribui automaticamente o tráfego de entrada entre várias instâncias de Amazon EC2 (ou outros recursos como containers e funções Lambda) para garantir alta disponibilidade para as aplicações. O objetivo principal do ELB é balancear a carga de tráfego entre vários servidores ou recursos, garantindo que nenhum servidor fique sobrecarregado, e que o tráfego seja distribuído de maneira eficiente.<br>
O ELB pode se ajustar automaticamente ao aumento ou diminuição do tráfego, redirecionando as requisições para instâncias EC2 disponíveis. Ele funciona bem com Auto Scaling Groups, permitindo que o número de instâncias EC2 aumente ou diminua conforme a demanda de tráfego.

## Tipos de ELB
- Application Load Balancer (ALB): Ideal para aplicações HTTP/HTTPS: O ALB é o tipo de ELB recomendado para balancear tráfego HTTP e HTTPS. Ele trabalha no nível da camada 7 (Aplicação) do modelo OSI, o que significa que ele pode fazer roteamento baseado em URLs, cabeçalhos HTTP, cookies, etc.
- Network Load Balancer (NLB): Ideal para aplicações de alto desempenho e baixa latência: O NLB opera na camada 4 (Transporte) e é projetado para altos volumes de tráfego com baixa latência. Ele é adequado para aplicações que exigem transporte TCP/UDP e alta performance.

## Segurança 
- O ELB oferece suporte a criptografia de ponta a ponta, usando SSL/TLS para proteger os dados em trânsito entre os clientes e os servidores. Você pode configurar certificados SSL no ELB para garantir a comunicação segura.
- Também pode ser integrado com AWS WAF para proteger suas aplicações contra ameaças da web.

## :books: Referências
 - *https://docs.aws.amazon.com/elasticloadbalancing/?icmpid=docs_homepage_networking*
<br />
<br />