# Pegadinhas — Módulo 2

## Famílias de instância

O enunciado quase nunca diz o nome da família. Ele descreve o **gargalo**:

| Sintoma no texto | Família |
| --- | --- |
| “processamento pesado de CPU”, encoding, HPC | Compute optimized |
| “grande conjunto de dados na memória”, SAP, Redis enorme | Memory optimized |
| “GPU”, “inferência”, “transcodificação de vídeo” | Accelerated computing |
| “milhões de IOPS locais”, NoSQL de alta taxa | Storage optimized |
| “servidor web”, “balanceado”, “dev/test” | General purpose |

Não confunda **tipo de instância** (família/tamanho) com **modelo de preço** (On-Demand/Spot). São eixos diferentes: você escolhe os dois.

## On-Demand vs Spot vs RI vs Savings Plans vs Dedicated Hosts

| Se o texto enfatiza… | Não marque… | Marque… |
| --- | --- | --- |
| Pode ser interrompido / fault-tolerant / batch | RI | Spot |
| Começar hoje, sem contrato | Savings Plans | On-Demand |
| Uso constante 24×7 por 1–3 anos | Spot | RI ou Savings Plans |
| Flexibilidade entre famílias/Regiões com desconto | RI clássica rígida | Compute Savings Plans |
| BYOL Windows/SQL preso a soquete | Dedicated Instances (conceito vizinho) | Dedicated **Hosts** |
| Isolamento de hardware por compliance | Spot | Dedicated Hosts |

Spot **não** é para banco primário nem para sessão de usuário que não pode cair.

Reserved Instance **não** é o mesmo que “reservar capacidade em outra AZ no Auto Scaling” — isso é *capacity*, não o produto RI.

## CloudFormation vs Elastic Beanstalk vs CLI

| Palavra-chave | Serviço |
| --- | --- |
| Template YAML/JSON, stack, IaC, repetir em várias contas | CloudFormation |
| Upload do código, plataforma gerencia a infra padrão | Elastic Beanstalk |
| Comando `aws ec2 run-instances` | CLI |
| Programador chama API | SDK |
| Assistente gráfico | Console |

Elastic Beanstalk **usa** EC2 (e frequentemente ELB/Auto Scaling) por baixo. Não é substituto de Lambda (isso é módulo 3).

## Scaling

- **Vertical** ≠ Auto Scaling. Auto Scaling da AWS, no discurso da prova, é **horizontal**.
- Mínimo 2 + ELB em 2 AZs = disponibilidade, não só performance.
- Subir o tipo da instância na mão = vertical (scale **up**).
- Acrescentar instâncias = horizontal (scale **out**).

## Load balancers

| Tráfego | Balancer |
| --- | --- |
| HTTP, HTTPS, host/path | ALB |
| TCP/UDP, latência extrema | NLB |
| Firewall / appliance na VPC | Gateway Load Balancer |
| “Classic” | Legado; raramente a melhor resposta atual |

ELB **não** substitui Auto Scaling: um distribui tráfego, o outro muda a quantidade de destinos.

Security Group do ELB vs da instância: o desenho comum é cliente → ELB → instâncias. A prova de redes (módulo 5) aprofunda; aqui lembre que o ELB é o ponto de entrada.

## SQS vs SNS vs ELB

| Precisa… | Serviço |
| --- | --- |
| Segurar trabalho até um worker poder processar | SQS |
| Fan-out: avisar N destinos ao mesmo tempo | SNS |
| Dividir HTTP entre instâncias saudáveis agora | ELB |

Não use ELB como fila. Não use SQS para balancear HTTP de usuário final em tempo real.
