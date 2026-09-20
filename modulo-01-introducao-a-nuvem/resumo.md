# Resumo — Módulo 1

Revisão de 5–10 minutos. Se algo não sair de cabeça, volte aos flashcards.

## Computação em nuvem

Entrega **sob demanda** de recursos de TI (compute, storage, banco, rede) **pela internet**, com preço **pay-as-you-go**. Você não compra o data center: aluga capacidade e paga pelo uso.

## Modelos de implantação

| Modelo | Ideia | Quando aparece na prova |
| --- | --- | --- |
| **Nuvem (cloud)** | Tudo roda na AWS | “migrar 100%”, “sem data center próprio” |
| **On-premises** | Tudo no data center da empresa (às vezes chamado de *private cloud*) | “controle total do hardware”, virtualização interna |
| **Híbrido** | Parte na nuvem + parte on-premises, conectadas | “legado que não pode sair agora”, “estourar capacidade na nuvem” |

## Benefícios da Nuvem AWS

Memorize o *porquê*, não a lista decorada:

1. **Trocar CapEx por OpEx** — deixa de investir pesado em servidores; paga variável.
2. **Economia de escala** — a AWS compra em volume; o preço unitário cai para você.
3. **Parar de adivinhar capacidade** — sobe e desce conforme a demanda (elasticidade).
4. **Velocidade e agilidade** — provisionar em minutos, não em semanas.
5. **Parar de operar data center** — menos energia, refrigeração, rack, equipe de chão.
6. **Ir global em minutos** — copiar a stack para outra Região.

Outras palavras que a prova usa no mesmo bloco: **alta disponibilidade**, **elasticidade**, **agilidade**, **confiabilidade**.

## Infraestrutura global (visão do módulo 1)

- **Região**: área geográfica com várias AZs. Você escolhe a Região (latência, compliance, preço, serviços disponíveis).
- **Availability Zone (AZ)**: um ou mais data centers isolados (energia, rede, prédio). Mínimo típico: **3 AZs por Região**.
- Isolamento entre AZs = falha em uma AZ não derruba as outras → **alta disponibilidade**.

Edge locations, CloudFront, Local Zones e Wavelength aprofundam no módulo 4. Aqui basta: Região agrupa AZs; AZ é o tijolo de disponibilidade.

## Modelo de responsabilidade compartilhada

Frase de ouro: **AWS protege a nuvem; o cliente protege o que está na nuvem.**

| AWS (segurança *da* nuvem) | Cliente (segurança *na* nuvem) |
| --- | --- |
| Data centers, hardware, hipervisor | Dados do cliente |
| Infraestrutura global (Regiões, AZs, edges) | Gestão de identidade (IAM, quem acessa o quê) |
| Rede e virtualização de base | Configuração: security groups, SO e patches no EC2 |
| Serviços gerenciados na camada de plataforma | Criptografia configurável, classificação de dados |

A fronteira **muda conforme o serviço**:

- **EC2**: cliente patcha o sistema operacional da instância.
- **RDS / Lambda**: a AWS cuida do SO e da plataforma; o cliente ainda cuida de dados, IAM e configuração.

Itens frequentemente **compartilhados** no discurso da prova: criptografia, gestão de identidade em alguns desenhos, configuração de rede.

## Economia da nuvem (gancho para o exame)

- **Custo fixo** (on-premises): servidor comprado, depreciação, sala fria — pague mesmo ocioso.
- **Custo variável** (nuvem): paga o que usa; rightsizing e desligar o que não precisa.
- **Rightsizing**: escolher o tamanho certo do recurso, não o maior “por garantia”.
