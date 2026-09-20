# Pegadinhas — Módulo 1

Comparações que a prova usa para distrair.

## Nuvem vs on-premises vs híbrido

| Se o enunciado fala… | Resposta |
| --- | --- |
| Tudo na AWS, sem hardware próprio | Nuvem |
| Servidores no prédio da empresa | On-premises |
| Mainframe fica, site novo na AWS | Híbrido |
| “Estourar” pico na nuvem e o resto local | Híbrido (burst) |

Não chame híbrido de “multi-cloud”. Multi-cloud é várias nuvens públicas (AWS + Azure, etc.). A prova de Cloud Practitioner foca AWS + on-premises = híbrido.

## Benefícios que se misturam

| Termo | Significa | Não é |
| --- | --- | --- |
| Elasticidade | Ajustar capacidade automaticamente | Alta disponibilidade |
| Escalabilidade | Crescer (muitas vezes na mão ou com plano) | O mesmo que elasticidade; elasticidade implica sobe *e desce* |
| Agilidade | Velocidade para criar/experimentar | Barato automaticamente |
| Alta disponibilidade | Continuar de pé se um componente falha | Backup (backup é recuperação, não uptime) |
| Economia de escala | AWS compra barato em volume e repassa | Desconto de Reserved Instance (isso é modelo de preço) |

## Região vs AZ

- **Região** = geografia (São Paulo, N. Virginia). Latência e compliance vivem aqui.
- **AZ** = isolamento dentro da Região. HA de aplicação típica = **multi-AZ**.
- Uma AZ **não** é “um servidor”. É data center(s) inteiro(s).
- Replicar entre **Regiões** é disaster recovery / presença global — não é o mínimo de HA.

## Responsabilidade compartilhada — as armadilhas clássicas

| Recurso / tarefa | Quase sempre… |
| --- | --- |
| Hardware, data center, hipervisor | AWS |
| SO e patches no **EC2** | Cliente |
| SO e patches no **RDS / Lambda / ECS Fargate** | AWS (plataforma gerenciada) |
| Configurar security group | Cliente |
| Dados e classificação | Cliente |
| IAM users, políticas, MFA | Cliente |
| Criptografia | Muitas vezes *compartilhada*: AWS oferece o recurso; cliente liga e gerencia chaves quando aplicável |

Pegadinha favorita: “quem patcha o SO?” — a resposta **depende do serviço**. EC2 ≠ RDS.

Outra: o cliente **nunca** perde a responsabilidade pelos **próprios dados**, mesmo em serviço 100% gerenciado.

## Economia

- Servidor ocioso on-premises **já foi pago** (CapEx). Na nuvem, instância ociosa **ainda gera conta** — por isso rightsizing e desligar.
- “Illimited capacity” **não** é um benefício oficial. O benefício é **não precisar adivinhar** e poder escalar.
