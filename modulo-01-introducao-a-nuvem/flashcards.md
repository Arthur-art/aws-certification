# Flashcards — Módulo 1

Cubra a resposta. Fale em voz alta antes de revelar.

## Computação e modelos

**P: O que é computação em nuvem em uma frase?**  
R: Entrega sob demanda de recursos de TI pela internet, com pagamento conforme o uso.

**P: Qual a diferença entre CapEx e OpEx neste contexto?**  
R: CapEx é investimento grande em hardware próprio. OpEx é gasto operacional variável (conta da AWS).

**P: Quando a prova descreve “conectar o data center legado à AWS”, qual modelo é?**  
R: Híbrido.

**P: Private cloud / on-premises significa o quê?**  
R: Recursos no data center da empresa, usando virtualização própria — não é a Nuvem AWS pública.

**P: Cloud-based deployment significa o quê?**  
R: Aplicação inteira na nuvem (nascida na nuvem ou migrada 100%).

## Benefícios

**P: Cite três benefícios da Nuvem AWS que caem em prova.**  
R: Qualquer trio sólido: economia de escala; elasticidade (não adivinhar capacidade); agilidade; ir global em minutos; trocar CapEx por variável; não manter data center.

**P: Elasticidade vs agilidade — como separar?**  
R: Elasticidade = escala recursos para cima/baixo com a demanda. Agilidade = lançar e experimentar rápido (minutos, não meses).

**P: Alta disponibilidade, em termos de infra AWS, apoia-se em quê?**  
R: Várias Availability Zones (e, em desenhos maiores, várias Regiões).

## Infra global

**P: O que é uma Região AWS?**  
R: Área geográfica que contém um conjunto de AZs isoladas.

**P: O que é uma Availability Zone?**  
R: Um ou mais data centers com energia, rede e conectividade redundantes, fisicamente separados das outras AZs da mesma Região.

**P: Por que usar mais de uma AZ?**  
R: Se uma AZ cai, a aplicação continua nas outras.

**P: Quem escolhe a Região?**  
R: O cliente — por latência dos usuários, leis de dados, preço e serviços disponíveis.

## Responsabilidade compartilhada

**P: Frase para gravar o modelo compartilhado.**  
R: AWS = segurança *da* nuvem. Cliente = segurança *na* nuvem.

**P: Patch do sistema operacional de uma instância EC2: de quem é?**  
R: Do cliente.

**P: Segurança física do data center: de quem é?**  
R: Da AWS.

**P: Dados que a empresa coloca no S3: de quem é a responsabilidade?**  
R: Do cliente (o que guardar, quem acessa, criptografia configurada).

**P: No Lambda ou no RDS, o patch do SO da plataforma é de quem?**  
R: Da AWS. O cliente ainda responde por dados, permissões e configuração da aplicação.

**P: IAM (quem pode fazer o quê na conta): de quem é?**  
R: Do cliente.
