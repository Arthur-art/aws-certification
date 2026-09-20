# Flashcards — Módulo 2

Cubra a resposta. Fale em voz alta antes de revelar.

## EC2 e tipos

**P: O que é Amazon EC2?**  
R: Serviço de servidores virtuais (instâncias) na AWS, com controle do sistema operacional.

**P: Instância otimizada para memória serve para quê?**  
R: Workloads que precisam de muita RAM (banco in-memory, cache grande).

**P: GPU / treino de ML aponta para qual família?**  
R: Computação acelerada.

**P: Web server simples, CPU e RAM equilibrados?**  
R: Uso geral (*general purpose*).

**P: Muito I/O de disco local, data warehouse?**  
R: Otimizada para armazenamento.

## Provisionamento

**P: Console vs CLI — diferença de uma linha?**  
R: Console é interface gráfica pontual. CLI é comando/scriptável.

**P: Quando a prova fala em “infraestrutura como código, template repetível”?**  
R: AWS CloudFormation.

**P: Você envia o código da aplicação e a AWS monta EC2 + load balancer?**  
R: AWS Elastic Beanstalk.

**P: Provisionar recursos de dentro de um programa Java/Python?**  
R: AWS SDK.

## Preços

**P: Sem compromisso, começa agora, carga irregular?**  
R: On-Demand.

**P: Até ~90% de desconto, mas a AWS pode interromper?**  
R: Spot Instances.

**P: Compromisso de 1 ou 3 anos em capacidade estável?**  
R: Reserved Instances e/ou Savings Plans.

**P: Qual a diferença mental Savings Plans vs Reserved Instances?**  
R: Savings Plans comprometem **dólar/hora** (mais flexível). RI compromete **tipo de instância** de forma mais rígida.

**P: Licenças vinculadas a núcleo físico / host dedicado?**  
R: Dedicated Hosts.

**P: Batch que pode recomeçar se morrer no meio?**  
R: Spot.

## Scaling e ELB

**P: Vertical vs horizontal?**  
R: Vertical = máquina maior. Horizontal = mais máquinas.

**P: Três números do Auto Scaling?**  
R: Mínimo, desejado, máximo.

**P: Além de escalar, o Auto Scaling também faz o quê com instância doente?**  
R: Substitui (self-healing).

**P: HTTP/HTTPS, roteamento por caminho de URL?**  
R: Application Load Balancer.

**P: TCP de altíssima performance / milhões de conexões?**  
R: Network Load Balancer.

**P: Por que ELB + várias AZs?**  
R: Distribui carga e sobrevive à queda de uma AZ.

## Filas

**P: Fila para desacoplar microserviços?**  
R: Amazon SQS.

**P: Um evento, muitos inscritos (e-mail + Lambda + SQS)?**  
R: Amazon SNS.

**P: SQS garante que o consumidor está online no momento do envio?**  
R: Não. A mensagem espera na fila.
