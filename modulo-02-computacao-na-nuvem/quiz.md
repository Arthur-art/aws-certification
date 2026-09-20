# Quiz — Módulo 2

Faça sem consultar o resumo. Gabarito comentado no final.

## Questões

**1.** Uma startup precisa de servidores Linux com controle total do sistema operacional, para um aplicativo monolítico. Qual serviço atende melhor?

- A) AWS Lambda
- B) Amazon EC2
- C) Amazon SQS
- D) Amazon CloudFront

**2.** Um workload de treino de modelo de machine learning precisa de GPUs. Qual família de instância EC2 se encaixa?

- A) Uso geral
- B) Otimizada para memória
- C) Computação acelerada
- D) Otimizada para armazenamento

**3.** A equipe quer descrever a infraestrutura em um arquivo e recriar o mesmo ambiente em outra conta AWS. Qual serviço usar?

- A) AWS Elastic Beanstalk
- B) Amazon EC2 Auto Scaling
- C) AWS CloudFormation
- D) Elastic Load Balancing

**4.** Desenvolvedores querem enviar só o código da aplicação web e deixar a AWS provisionar EC2, Auto Scaling e load balancer. Qual serviço?

- A) AWS CloudFormation
- B) AWS Elastic Beanstalk
- C) Amazon SNS
- D) Dedicated Hosts

**5.** Um job de processamento de logs pode ser interrompido e reiniciado. O time quer o menor custo possível. Qual modelo de preço de EC2?

- A) On-Demand
- B) Dedicated Hosts
- C) Spot Instances
- D) Reserved Instances de 3 anos sem flexibilidade de interrupção

**6.** Aplicação de e-commerce com tráfego estável 24 horas, 7 dias, pelos próximos 3 anos. Qual abordagem reduz custo com menos risco de interrupção?

- A) Somente Spot
- B) Savings Plans ou Reserved Instances
- C) Somente Dedicated Hosts
- D) Desligar o Auto Scaling

**7.** “Aumentar a instância de t3.medium para t3.xlarge” descreve qual tipo de scaling?

- A) Horizontal (scale out)
- B) Vertical (scale up)
- C) Predictive scaling apenas
- D) Load balancing

**8.** Qual combinação melhor descreve um site resiliente a falha de uma AZ e a picos de CPU?

- A) Uma instância grande On-Demand numa AZ só
- B) ELB + grupo de Auto Scaling em várias AZs
- C) Apenas SNS
- D) Apenas CloudFormation sem instâncias

**9.** Uma API HTTP precisa rotear `/users` e `/orders` para grupos diferentes de instâncias. Qual load balancer?

- A) Network Load Balancer
- B) Gateway Load Balancer
- C) Application Load Balancer
- D) Dedicated Host

**10.** O serviço A envia tarefas que o serviço B processa quando estiver livre, sem os dois precisarem estar ativos ao mesmo tempo. Qual serviço desacopla esse fluxo?

- A) Elastic Load Balancing
- B) Amazon SQS
- C) Amazon CloudFront
- D) Amazon EC2 Auto Scaling

**11.** Marketing precisa que o mesmo evento “pedido criado” dispare e-mail, uma função e uma fila. Qual serviço?

- A) Amazon SQS apenas
- B) Amazon SNS
- C) Network Load Balancer
- D) Spot Fleet

**12.** Qual afirmação sobre Amazon EC2 Auto Scaling é verdadeira?

- A) Só faz scaling vertical
- B) Pode aumentar, reduzir e substituir instâncias não saudáveis
- C) Substitui a necessidade de IAM
- D) É um modelo de preço do EC2

---

## Gabarito

1. **B** — Controle de SO = EC2. Lambda é serverless (módulo 3). SQS é fila. CloudFront é CDN.
2. **C** — GPU = computação acelerada.
3. **C** — Template repetível = CloudFormation. Beanstalk é deploy de app, não IaC genérico.
4. **B** — PaaS: você manda o código, a AWS monta a infra web padrão.
5. **C** — Interrompível + custo mínimo = Spot. RI/On-Demand/Dedicated não são a melhor resposta.
6. **B** — Carga estável e longa = compromisso (Savings Plans ou RI). Spot pode derrubar a loja.
7. **B** — Trocar o tamanho da *mesma* máquina = vertical.
8. **B** — ELB distribui; Auto Scaling em várias AZs cobre pico e falha de AZ.
9. **C** — HTTP + roteamento por path = ALB (camada 7). NLB é TCP/UDP.
10. **B** — Fila assíncrona = SQS. ELB exige destinos vivos agora.
11. **B** — Fan-out pub/sub = SNS (pode ter SQS como um dos inscritos).
12. **B** — Horizontal + health: sobe, desce e substitui. Não é preço nem IAM.
