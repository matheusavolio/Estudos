A AWS oferece um amplo conjunto de produtos globais baseados na nuvem que podem ser usados como componentes básicos para arquiteturas de nuvem comuns. Veja a seguir como esses produtos baseados na nuvem são organizados.

---
---
#### Serviços fundamentais da AWS
![[Pasted image 20240909171658.png]]
Como discutido anteriormente, a infraestrutura global da AWS pode ser dividida em três elementos: regiões, zonas de disponibilidade e pontos de presença, que incluem pontos de presença. Essa infraestrutura fornece a plataforma para um amplo conjunto de serviços, como redes, armazenamento, serviços de computação e bancos de dados. Esses serviços são fornecidos como um utilitário sob demanda disponível em segundos, com definição de preço de pagamento conforme o uso.

---
---
#### Categorias de serviços da AWS
![[Pasted image 20240909171755.png]]
A AWS oferece um amplo conjunto de serviços baseados na nuvem. Existem 23 categorias diferentes de produtos ou serviços, e cada categoria consiste em um ou mais serviços. Este curso não tentará apresentá-lo a cada serviço. Em vez disso, o foco deste curso é os serviços que são mais amplamente utilizados e oferecem a melhor introdução à Nuvem AWS. Esse curso também se concentra em serviços com maior probabilidade de serem cobertos no exame AWS Certified Cloud Practitioner.

As categorias que este curso discutirá são destacadas no slide: Computação, Gerenciamento de custos, Banco de dados, Gerenciamento e governança, Redes e entrega de conteúdo, Segurança, Identidade e Conformidade e Armazenamento.

Para saber mais sobre os produtos da AWS, consulte: [http://aws.amazon.com/products](http://aws.amazon.com/products). Todos os produtos da AWS são organizados nas categorias de serviço que são mostradas aqui. Por exemplo, se você clicar em Compute, verá que o Amazon Elastic Compute Cloud (Amazon EC2) está primeiro na lista. A categoria de computação também lista muitos outros produtos e serviços.

Se você clicar em Amazon EC2, ele o levará para a página do Amazon EC2. Cada página de produto fornece uma descrição detalhada do produto e lista alguns de seus benefícios.

Explore os diferentes grupos de serviços para entender as categorias e os serviços dentro deles. Agora que você sabe como localizar informações sobre diferentes serviços, este módulo discutirá as categorias de serviço destacadas . Os próximos sete slides listam os serviços individuais, dentro de cada uma das categorias destacadas acima que este curso discutirá.

---
---
#### Categoria de serviço de armazenamento AWS

![[Pasted image 20240909171937.png]]

Os serviços de armazenamento da AWS incluem os serviços listados aqui e muitos outros.

O Amazon Simple Storage Service (Amazon S3) é um serviço de armazenamento de objetos que oferece escalabilidade, disponibilidade de dados, segurança e performance. Use-o para armazenar e proteger qualquer quantidade de dados para sites, aplicativos móveis, backup e restauração, arquivamento, aplicativos empresariais, dispositivos da Internet das Coisas (IoT) e análises de big data.

O Amazon Elastic Block Store (Amazon EBS) é um armazenamento em blocos de alta performance projetado para uso com o Amazon EC2 para cargas de trabalho com throughput e com uso intensivo de transações. Ele é usado para várias cargas de trabalho, como bancos de dados relacionais e não relacionais, aplicativos corporativos, aplicativos em contêiner, mecanismos de análise de big data, sistemas de arquivos e fluxos de trabalho de mídia.

O Amazon Elastic File System (Amazon EFS) fornece um sistema gerenciado de arquivos NFS, escalável e elástico para uso com os serviços de nuvem AWS e recursos locais. Ele é desenvolvido para escalar sob demanda, aumentando e diminuindo automaticamente à medida que você adiciona e remove arquivos. Ele reduz a necessidade de provisionar e gerenciar capacidade para acomodar o crescimento.

O Amazon Simple Storage Service Glacier é uma classe de armazenamento na nuvem do Amazon S3 segura, durável e de custo extremamente baixo para arquivamento de dados e backup de longo prazo. Ele foi projetado para fornecer 11 noves de durabilidade e para fornecer recursos abrangentes de segurança e conformidade para cumprir requisitos normativos rigorosos.

---
---
#### Categoria de serviço de banco de dados


Os serviços de banco de dados da AWS incluem os serviços listados aqui e muitos outros.

O Amazon Relational Database Service (Amazon RDS) facilita configurar, operar e escalar um banco de dados relacional na nuvem. Ele oferece capacidade redimensionável e automatiza tarefas demoradas de administração, como provisionamento de hardware, configuração de bancos de dados, aplicação de patches e backups.

O Amazon Aurora é um banco de dados relacional compatível com MySQL e PostgreSQL. É até cinco vezes mais rápido que os bancos de dados MySQL padrão e três vezes mais rápido que os bancos de dados PostgreSQL padrão.

O Amazon Redshift permite executar consultas analíticas em petabytes de dados armazenados localmente no Amazon Redshift e diretamente em exabytes de dados armazenados no Amazon S3. Ele oferece performance rápida em qualquer escala.

O Amazon DynamoDB é um banco de dados de documentos e chave-valor que oferece performance inferior a 10 milissegundos em qualquer escala, com segurança incorporada, backup e restauração e armazenamento em cache na memória.

---
---
![[Pasted image 20240909172016.png]]
Os serviços de banco de dados da AWS incluem os serviços listados aqui e muitos outros.

O Amazon Relational Database Service (Amazon RDS) facilita configurar, operar e escalar um banco de dados relacional na nuvem. Ele oferece capacidade redimensionável e automatiza tarefas demoradas de administração, como provisionamento de hardware, configuração de bancos de dados, aplicação de patches e backups.

O Amazon Aurora é um banco de dados relacional compatível com MySQL e PostgreSQL. É até cinco vezes mais rápido que os bancos de dados MySQL padrão e três vezes mais rápido que os bancos de dados PostgreSQL padrão.

O Amazon Redshift permite executar consultas analíticas em petabytes de dados armazenados localmente no Amazon Redshift e diretamente em exabytes de dados armazenados no Amazon S3. Ele oferece performance rápida em qualquer escala.

O Amazon DynamoDB é um banco de dados de documentos e chave-valor que oferece performance inferior a 10 milissegundos em qualquer escala, com segurança incorporada, backup e restauração e armazenamento em cache na memória.

---
---
#### Categoria de serviço de rede e entrega de conteúdo
![[Pasted image 20240909172049.png]]
Os serviços de rede e entrega de conteúdo da AWS incluem os serviços listados aqui e muitos outros.

O Amazon Virtual Private Cloud (Amazon VPC) permite provisionar seções logicamente isoladas da Nuvem AWS.

O Elastic Load Balancing distribui automaticamente o tráfego de entrada dos aplicativos entre vários destinos, como instâncias do Amazon EC2, contêineres, endereços IP e funções do Lambda.

O Amazon CloudFront é um serviço rápido de rede de entrega de conteúdo (CDN) que entrega dados, vídeos, aplicativos e interfaces de programação de aplicativos (APIs) para clientes em todo o mundo, com baixa latência e altas velocidades de transferência.

O AWS Transit Gateway é um serviço que permite que os clientes conectem suas Amazon Virtual Private Clouds (VPCs) e suas redes locais a um único gateway.

O Amazon Route 53 é um serviço Web de Domain Name System (DNS) na nuvem escalável projetado para oferecer uma maneira confiável de rotear usuários finais para aplicativos da Internet. Ele converte nomes (como www.exemplo.com) em endereços IP numéricos (como 192.0.2.1) que os computadores usam para se conectarem uns aos outros.

O AWS Direct Connect oferece uma maneira de estabelecer uma conexão de rede privada dedicada do datacenter ou escritório para a AWS, o que pode reduzir os custos de rede e aumentar o throughput da largura de banda.

A VPN da AWS fornece um túnel privado seguro da sua rede ou dispositivo para a rede global da AWS.

---
---
#### Categoria de serviços de segurança, identidade e conformidade
![[Pasted image 20240909172138.png]]
Os serviços de segurança, identidade e conformidade da AWS incluem os serviços listados aqui e muitos outros.

O AWS Identity and Access Management (IAM) permite que você gerencie o acesso aos serviços e recursos da AWS com segurança. Ao usar o IAM, você pode criar e gerenciar usuários e grupos da AWS. Você pode usar permissões do IAM para permitir e negar acesso de usuários e grupos aos recursos da AWS.

O AWS Organizations permite restringir quais serviços e ações são permitidos nas suas contas.

O Amazon Cognito permite adicionar cadastro, login e controle de acesso de usuários aos aplicativos Web e para dispositivos móveis.

OAWS Artifact oferece acesso sob demanda a relatórios de segurança e conformidade da AWS e a contratos on-line selecionados.

O AWS Key Management Service (AWS KMS) permite criar e gerenciar chaves. Você pode usar o AWS KMS para controlar o uso da criptografia em uma grande variedade de serviços da AWS e em seus aplicativos.

O AWS Shield é um serviço gerenciado de proteção contra a negação de serviço distribuída (DDoS) que protege aplicativos executados na AWS.

---
---
#### Categoria de serviço de gerenciamento de custos da AWS
![[Pasted image 20240909172345.png]]
Os serviços de gerenciamento de custos da AWS incluem os serviços listados aqui e outros.

O Relatório de custos e uso da AWS contém o conjunto mais abrangente de dados de custos e uso da AWS disponíveis, incluindo metadados adicionais sobre serviços, definição de preço e reservas da AWS.

O Orçamentos da AWS permite que você defina orçamentos personalizados que enviam alertas quando o uso ou os custos excedem (ou têm previsão de exceder) o valor orçado.

O AWS Cost Explorer tem uma interface fácil de usar que permite visualizar, compreender e gerenciar seus custos e uso da AWS ao longo do tempo.

---
---
#### Categoria de serviço de gerenciamento e governança
![[Pasted image 20240909172415.png]]
Os serviços de gerenciamento e governança da AWS incluem os serviços listados aqui e outros.

O Console de Gerenciamento da AWS fornece uma interface de usuário baseada na web para acessar sua conta da AWS.

O AWS Config fornece um serviço que ajuda você a rastrear o inventário de recursos e as alterações.

O Amazon CloudWatch permite monitorar recursos e aplicativos.

O AWS Auto Scaling oferece recursos que permitem escalar vários recursos para atender à demanda.

A interface de linha de comando da AWS fornece uma ferramenta unificada para gerenciar serviços da AWS.

O AWS Trusted Advisor ajuda você a otimizar a performance e a segurança.

O AWS Well-Architected Tool oferece ajuda para revisar e aprimorar suas cargas de trabalho.

O AWS CloudTrail rastreia a atividade do usuário e o uso da API.

---
---
