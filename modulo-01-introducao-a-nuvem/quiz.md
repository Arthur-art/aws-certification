# Quiz — Módulo 1

Faça sem consultar o resumo. Gabarito comentado no final.

## Questões

**1.** Qual definição melhor descreve computação em nuvem?

- A) Comprar servidores em leasing e instalá-los no data center da empresa
- B) Entrega sob demanda de recursos de TI pela internet, com pagamento conforme o uso
- C) Virtualizar todos os desktops da empresa com software local
- D) Contratar um link dedicado entre duas filiais

**2.** Uma empresa quer manter o sistema de folha no data center próprio e hospedar o site institucional na AWS. Qual modelo de implantação é esse?

- A) Somente nuvem
- B) On-premises
- C) Híbrido
- D) Multi-AZ

**3.** Qual benefício da Nuvem AWS descreve a troca de investimento pesado em hardware por gasto variável?

- A) Ir global em minutos
- B) Trocar despesas de capital por despesas variáveis
- C) Alta disponibilidade
- D) AWS Shared Responsibility Model

**4.** Por que uma aplicação é implantada em pelo menos duas Availability Zones?

- A) Para reduzir o preço da Região
- B) Para cumprir automaticamente qualquer lei de residência de dados
- C) Para continuar disponível se uma AZ falhar
- D) Porque cada AZ é uma Região diferente

**5.** Quem é responsável pela segurança física dos data centers da AWS?

- A) O cliente, via security groups
- B) O parceiro de Marketplace
- C) A AWS
- D) O usuário root da conta, pessoalmente

**6.** Em uma instância Amazon EC2, quem aplica patches no sistema operacional convidado?

- A) Sempre a AWS, em qualquer serviço
- B) O cliente
- C) O AWS Trusted Advisor
- D) O CloudFront

**7.** Uma equipe usa Amazon RDS. Qual afirmação está correta sobre o modelo compartilhado?

- A) O cliente patcha o sistema operacional do host do banco
- B) A AWS é responsável pelos dados inseridos nas tabelas
- C) A AWS gerencia a infraestrutura e a plataforma do banco; o cliente segue responsável por dados, acessos e configuração
- D) Não há responsabilidade do cliente em serviços gerenciados

**8.** Qual cenário ilustra melhor **elasticidade**?

- A) Abrir um chamado no Support
- B) Aumentar e reduzir automaticamente o número de instâncias conforme o tráfego
- C) Escolher a Região mais próxima dos usuários
- D) Criptografar um bucket S3

**9.** Uma empresa escolhe a Região sa-east-1. Qual NÃO é um motivo típico para escolher uma Região?

- A) Latência para os usuários
- B) Requisitos legais de onde os dados podem ficar
- C) Cor do logo da AWS nessa Região
- D) Preço e serviços disponíveis

**10.** Qual tarefa é responsabilidade do cliente na Nuvem AWS?

- A) Manutenção dos hipervisores
- B) Controle de quem acessa os dados (IAM e políticas)
- C) Substituição de disco falho no data center
- D) Energia redundante das AZs

---

## Gabarito

1. **B** — Definição padrão: on-demand + internet + pay-as-you-go.
2. **C** — Parte local + parte AWS = híbrido. Multi-AZ é disponibilidade, não modelo de implantação.
3. **B** — CapEx → OpEx/variável. Shared responsibility é segurança, não benefício econômico.
4. **C** — AZs isoladas: falha em uma não derruba a outra. AZ não é Região.
5. **C** — Segurança *da* nuvem (física) é AWS.
6. **B** — No EC2 o SO da instância é do cliente. Em RDS/Lambda a história muda.
7. **C** — Serviço gerenciado desloca o SO para a AWS; dados e IAM continuam com o cliente.
8. **B** — Elasticidade = escala sobe e desce com a demanda.
9. **C** — Critérios reais: latência, compliance, preço, features.
10. **B** — Identidade e acesso são segurança *na* nuvem.
