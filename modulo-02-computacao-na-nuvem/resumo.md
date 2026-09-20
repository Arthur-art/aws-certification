# Resumo — Módulo 2

Revisão de 5–10 minutos.

## Amazon EC2

Máquina virtual na nuvem: você escolhe CPU, memória, armazenamento e rede, liga quando precisa e desliga quando não precisa. Controle do SO (Linux/Windows) — por isso, no modelo compartilhado, **patch do SO é do cliente**.

Use EC2 quando precisa de servidor “clássico”: aplicativo legado, controle do SO, workload que ainda não é serverless.

## Tipos de instância

A família diz **o recurso que está otimizado**:

| Família | Otimizada para | Exemplo de uso |
| --- | --- | --- |
| **Uso geral** | Balanço CPU/memória | Web, dev/test, pequenos bancos |
| **Otimizada para computação** | CPU | Batch, gaming, HPC científico |
| **Otimizada para memória** | RAM | Bancos in-memory, caches grandes |
| **Computação acelerada** | GPU / chips de IA | Machine learning, gráficos |
| **Otimizada para armazenamento** | Disco local de alta I/O | Data warehouse, arquivos sequenciais |

Na prova: leia o gargalo (CPU vs RAM vs disco vs GPU) e aponte a família.

## Como provisionar recursos

| Forma | Ideia | Palavra-chave |
| --- | --- | --- |
| **AWS Management Console** | Clique no browser | Visual, pontual, aprendizado |
| **AWS CLI** | Comandos no terminal | Script, automação simples |
| **SDKs** | Chamar AWS de dentro do código | Aplicação provisiona recursos |
| **AWS CloudFormation** | Infra como código (template) | Repetível, versão, várias contas/Regiões |
| **AWS Elastic Beanstalk** | Você manda o código; a AWS sobe EC2, load balancer, etc. | PaaS, “não quero montar a infra na mão” |

Console e CLI/SDK = **como você fala com a AWS**. CloudFormation = **o que deve existir, declarado**. Elastic Beanstalk = **deploy de aplicação com infra padrão**.

## Preços do EC2

| Modelo | Quando usar | Pegadinha |
| --- | --- | --- |
| **On-Demand** | Sem compromisso; pico, teste, irregular | Mais caro por hora; máxima flexibilidade |
| **Savings Plans** | Compromisso de **gasto** $/hora por 1 ou 3 anos | Flexível entre família/Região (Compute SP) |
| **Reserved Instances** | Compromisso de **instância** (família, Região…) 1 ou 3 anos | Menos flexível que Savings Plans; desconto alto se estável |
| **Spot** | Workload que pode ser **interrompida** | Até ~90% mais barato; a AWS pode reaver a capacidade |
| **Dedicated Hosts** | Servidor físico só seu | Licença BYOL, requisitos de compliance de host |

Regra prática: **interrupível → Spot**. **Estável 24×7 → Savings Plans / RI**. **Imprevisível → On-Demand**. **Licença amarrada a soquete/núcleo → Dedicated Host**.

## Scaling

- **Vertical**: cresce a **máquina** (t3.small → t3.large). Tem teto; em geral dá downtime para trocar o tipo.
- **Horizontal**: cresce a **quantidade** de máquinas. É o padrão na nuvem.

**Amazon EC2 Auto Scaling**:

- Sobe instâncias quando a métrica estoura (CPU, request count…)
- Desce quando acalma (economia)
- Substitui instância não saudável (disponibilidade)
- Trabalha com **mínimo / desejado / máximo**

Dynamic scaling (reage a métrica) vs predictive (antecipa padrão). Para a prova, o conceito basta: **ajusta capacidade sozinho e substitui falhas**.

## Elastic Load Balancing (ELB)

Distribui tráfego entre instâncias (em geral em **várias AZs**). Sem o load balancer, o cliente precisaria escolher um IP só — ponto único de falha.

| Tipo | Tráfego | Uso típico |
| --- | --- | --- |
| **Application Load Balancer (ALB)** | HTTP/HTTPS (camada 7) | Sites, APIs, path-based routing |
| **Network Load Balancer (NLB)** | TCP/UDP (camada 4), ultra baixa latência | Gaming, milhões de conexões |
| **Gateway Load Balancer** | Appliances de rede/segurança | Firewall, inspeção de tráfego |
| **Classic Load Balancer** | Legado | Aparece como “geração anterior”; prefira ALB/NLB |

ELB + Auto Scaling é o desenho clássico: o balancer aponta para um **grupo** que cresce e encolhe.

## Mensageria e filas (desacoplamento)

Mesmo que a lição venha no fim do módulo, cai no exame:

- **Amazon SQS**: fila. Produtor manda mensagem; consumidor puxa quando puder. Aplica-se a **desacoplar** e absorver pico. Pelo menos uma vez; o consumidor processa.
- **Amazon SNS**: pub/sub. Uma mensagem, **vários** inscritos (e-mail, Lambda, SQS…). Fan-out.
- **Amazon EventBridge** (nome que pode aparecer): barramento de eventos entre serviços.

SQS = “espera na fila”. SNS = “avisa todo mundo”.
