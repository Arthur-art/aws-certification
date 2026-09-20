# Exame AWS Certified Cloud Practitioner (CLF-C02)

Use este arquivo para lembrar **como a prova funciona**. O conteúdo em si está nas pastas dos módulos.

## O que a prova valida

Você precisa demonstrar, em nível fundamental (sem precisar programar ou projetar arquitetura):

- Explicar o valor da Nuvem AWS
- Entender o modelo de responsabilidade compartilhada
- Entender práticas de segurança
- Entender custos, economia e faturamento
- Descrever e posicionar serviços principais (computação, rede, banco, armazenamento)
- Identificar o serviço certo para um caso de uso comum

## Formato

| Item | Detalhe |
| --- | --- |
| Código | CLF-C02 |
| Questões | 65 (50 pontuam + 15 não pontuam e não são identificadas) |
| Tipos | Múltipla escolha (1 certa) e múltipla resposta (2+ certas) |
| Nota | Escala 100–1000; **mínimo para passar: 700** |
| Modelo | Compensatório: não precisa passar em cada domínio, só na prova inteira |
| Fora de escopo | Código, desenho de arquitetura, troubleshooting, implementação, testes de carga |

Pergunta em branco conta como errada. Não há penalidade por chute.

## Domínios e pesos

| Domínio | Peso | O que cai |
| --- | --- | --- |
| 1. Conceitos de nuvem | 24% | Benefícios, Well-Architected, migração/CAF, economia da nuvem |
| 2. Segurança e conformidade | 30% | Responsabilidade compartilhada, IAM, conformidade, serviços de segurança |
| 3. Tecnologia e serviços | 34% | Infra global, compute, storage, DB, rede, analytics, provisionamento |
| 4. Faturamento, preços e suporte | 12% | Modelos de preço, billing, Support Plans, Marketplace |

**Segurança (30%) + Tecnologia (34%) = 64% da prova.** Priorize esses dois na revisão.

## Como estudar pensando na prova

- A prova testa **qual serviço usar**, não como clicar no console.
- Distratores são respostas “quase certas”. Treine diferenças (S3 vs EBS, Security Group vs NACL, CloudWatch vs CloudTrail).
- Palavras-chave no enunciado quase sempre apontam um serviço: “fila” → SQS, “pub/sub” → SNS, “servidorless de função” → Lambda.

Mapa módulo do curso → domínio: [mapa-curso-exame.md](mapa-curso-exame.md).
