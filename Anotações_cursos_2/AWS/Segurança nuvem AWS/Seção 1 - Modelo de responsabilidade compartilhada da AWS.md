#### Módulo 4 - Segurança na Nuvem AWS
A segurança é a maior prioridade na Amazon Web Services (AWS). A AWS oferece um ambiente de computação em nuvem escalável projetado para oferecer alta disponibilidade e confiabilidade, além de fornecer as ferramentas que permitem executar uma grande variedade de aplicativos. Ajudar a proteger a confidencialidade, a integridade e a disponibilidade de seus sistemas e dados é essencial para a AWS, assim como manter a confiança e a convicção do cliente. Este módulo fornece uma introdução à abordagem da AWS à segurança, que inclui os controles no ambiente da AWS e alguns dos produtos e recursos da AWS que os clientes podem usar para cumprir os objetivos de segurança.

![[Pasted image 20240910142131.png]]

Segurança e conformidade são responsabilidades compartilhadas entre a AWS e o cliente. Esse modelo de responsabilidade compartilhada foi projetado para ajudar a reduzir a carga operacional do cliente. Ao mesmo tempo, para oferecer a flexibilidade e o controle do cliente que permitem a implantação de soluções de clientes na AWS, o cliente permanece responsável por alguns aspectos da segurança geral. A diferenciação de quem é responsável pelo quê normalmente se dá pelas expressões segurança "da" nuvem e segurança "na" nuvem.

A AWS opera, gerencia e controla os componentes desde a camada de virtualização de software até a segurança física das instalações em que os serviços da AWS operam. `A AWS é responsável pela proteção da infraestrutura que executa todos os serviços oferecidos na Nuvem AWS`. Essa infraestrutura é composta por hardware, software, redes e instalações que executam os Serviços de nuvem AWS.

`O cliente é responsável pela criptografia de dados em repouso e em trânsito`. O cliente também deve garantir que a rede esteja configurada para segurança e que as credenciais e os logins de segurança sejam gerenciados de maneira segura. Além disso, o cliente é responsável pela configuração de grupos de segurança e pela configuração do sistema operacional que é executado nas instâncias de computação que ele executa (incluindo atualizações e patches de segurança).

---
---


#### Responsabilidade da AWS: Segurança da nuvem

![[Pasted image 20240910142711.png]]

![[Pasted image 20240910142651.png]]

#ResponsabilidadesDaAWS:
•Segurança física dos datacenters
•Acesso controlado e baseado em necessidades
•Infraestrutura de hardware e software
•Desativação de armazenamento, registro em log de acesso ao sistema operacional (SO) do host e auditoria
•Infraestrutura de rede
•Detecção de intrusão
•Infraestrutura de virtualização
•Isolamento de instância

A AWS é responsável pela segurança da nuvem. Mas o que isso significa?

Sob o modelo de responsabilidade compartilhada da AWS, a AWS opera, gerencia e controla os componentes do sistema operacional host bare metal e da camada de virtualização do hipervisor até a segurança física das instalações em que os serviços operam. Isso significa que a AWS é responsável pela proteção da infraestrutura global que executa todos os serviços oferecidos na Nuvem AWS. A infraestrutura global inclui zonas de disponibilidade, pontos de presença e regiões da AWS.

A AWS é responsável pela infraestrutura física que hospeda seus recursos, incluindo:

•Segurança física de datacenters com acesso controlado e baseado em necessidades; localizados em instalações não identificadas, com guardas de segurança 24 horas por dia, 7 dias por semana; autenticação de dois fatores; revisão e registro em log de acesso; vigilância por vídeo; e desmagnetização e destruição de discos.

•Infraestrutura de hardware, como servidores, dispositivos de armazenamento e outros dispositivos dos quais a AWS depende.

•Infraestrutura de software, que hospeda sistemas operacionais, aplicativos de serviço e software de virtualização.

•Infraestrutura de rede, como roteadores, switches, load balancers, firewalls e cabeamento. A AWS também monitora continuamente a rede em limites externos, protege pontos de acesso e oferece infraestrutura redundante com detecção de intrusão.  

A proteção dessa infraestrutura é a maior prioridade da AWS. Embora você não possa visitar datacenters ou escritórios da AWS para ver essa proteção em primeira mão, a Amazon fornece vários relatórios de auditores terceirizados que verificaram nossa conformidade com diversos padrões e regulamentos de segurança de computadores.

---
---



#### Responsabilidade do cliente: segurança na nuvem
![[Pasted image 20240910142914.png]]
#ResponsabilidadesDoCliente:

- Sistema operacional da instância do Amazon Elastic Compute Cloud (Amazon EC2)
- incluindo aplicação de patches, manutenção
- Aplicações
- Senhas, acesso baseado em função etc.
- Configuração do grupo de segurança
- Firewalls baseados em host ou SO
- Incluindo sistemas de prevenção ou detecçãode intrusão
- Configurações de rede
- Gerenciamento de contas
- Configurações de permissão e login paracada usuário

Embora a infraestrutura de nuvem seja protegida e mantida pela AWS, os clientes são responsáveis pela segurança de tudo o que colocam na nuvem.

O cliente é responsável pelo que é implementado com o uso dos serviços da AWS e pelos aplicativos conectados à AWS. As etapas de segurança que você deve seguir dependem dos serviços que você usa e da complexidade do seu sistema.

As responsabilidades do cliente incluem selecionar e proteger qualquer sistema operacional de instância, proteger os aplicativos executados em recursos da AWS, configurações de grupos de segurança, configurações de firewall, configurações de rede e gerenciamento seguro de contas.

Quando os clientes usam os serviços da AWS, eles mantêm controle total sobre o conteúdo. Os clientes são responsáveis por gerenciar requisitos críticos de segurança de conteúdo, incluindo:

- Qual conteúdo eles escolhem armazenar na AWS
- Quais serviços da AWS são usados com o conteúdo
- Em qual país esse conteúdo é armazenado
- O formato e a estrutura desse conteúdo e se ele é mascarado, anonimizado ou criptografado
- Quem tem acesso a esse conteúdo e como esses direitos de acesso são concedidos, gerenciados e revogados

Os clientes mantêm o controle da segurança que escolhem implementar para proteger seus próprios dados, ambiente, aplicativos, configurações do IAM e sistemas operacionais.

---
---

#### Características do serviço e responsabilidade de segurança

![[Pasted image 20240910143224.png]]
![[Pasted image 20240910143233.png]]

![[Pasted image 20240910143648.png]]


Infraestrutura como um serviço (IaaS)
#IaaS_NaSegurança
- O cliente tem mais flexibilidade em relação à configuração de rede e armazenamento
- O cliente é responsável por gerenciar mais aspectos da segurança
- O cliente configura os controles de acesso

Plataforma como serviço (PaaS)
#PaaS_NaSegurança
- O cliente não precisa gerenciar a infraestrutura subjacente
- A AWS gerencia o sistema operacional, a aplicação de patches de banco de dados, a configuração de firewall e a recuperação de desastres
- O cliente pode se concentrar no gerenciamento de código ou dados

Software como serviço (SaaS)
#SaaS_NaSegurança
- O software é hospedado de maneira centralizada
- Licenciado em um modelo de assinatura ou pagamento conforme o uso.
- Os serviços normalmente são acessados por meio de um navegador da Web, um aplicativo móvel ou uma interface de programação de aplicativos (API)
- Os clientes não precisam gerenciar a infraestrutura que oferece suporte ao serviço

Infraestrutura como serviço (IaaS) refere-se a serviços que fornecem componentes básicos da TI, normalmente incluindo acesso para configuração de redes, computadores (virtuais ou em hardware dedicado) e espaço para o armazenamento de dados. Os serviços de nuvem que podem ser caracterizados como IaaS fornecem ao cliente o mais alto nível de flexibilidade e controle de gerenciamento sobre recursos de TI. Os serviços de IaaS são mais semelhantes aos recursos de computação locais existentes com os quais muitos departamentos de TI estão familiarizados atualmente.

Os serviços da AWS, como o Amazon EC2, podem ser categorizados como IaaS e, portanto, exigem que `o cliente execute todas as tarefas de configuração e gerenciamento de segurança necessárias. Os clientes que implantam instâncias do EC2 são responsáveis pela gestão do sistema operacional convidado (incluindo atualizações e patches de segurança)`, qualquer software de aplicativo instalado nas instâncias e pela configuração dos grupos de segurança que foram fornecidos pela AWS.

Plataforma como serviço (PaaS) refere-se a serviços que eliminam a necessidade de o cliente gerenciar a infraestrutura subjacente (hardware, sistemas operacionais etc.). Os serviços PaaS permitem que o cliente se concentre totalmente na implantação e no gerenciamento de aplicativos. `Os clientes não precisam se preocupar com a aquisição de recursos, o planejamento de capacidade, a manutenção de software ou a aplicação de patches.`

Software como serviço (SaaS) refere-se a serviços que fornecem software hospedado de maneira centralizada que geralmente é acessível por meio de um navegador da Web, aplicativo móvel ou interface de programação de aplicativos (API). O modelo de licenciamento para ofertas de SaaS normalmente é de assinatura ou pagamento conforme o uso. Com as ofertas de SaaS, `os clientes não precisam gerenciar a infraestrutura que oferece suporte ao serviço.` Alguns serviços da AWS, como AWS Trusted Advisor, AWS Shield e Amazon Chime, podem ser categorizados como ofertas de SaaS, considerando as características que têm.

O AWS Trusted Advisor é uma ferramenta on-line que analisa seu ambiente da AWS e fornece orientações e recomendações em tempo real para ajudar você a provisionar seus recursos seguindo as práticas recomendadas da AWS. O serviço Trusted Advisor é oferecido como parte do seu plano do AWS Support. Alguns dos recursos do Trusted Advisor são gratuitos para todas as contas, mas os clientes do Business Support e do Enterprise Support têm acesso ao conjunto completo de verificações e recomendações do Trusted Advisor.

O AWS Shield é um serviço gerenciado de proteção contra a negação de serviço distribuída (DDoS) que protege aplicativos executados na AWS. Ele fornece detecção e mitigações embutidas automáticas e sempre ativas que minimizam o tempo de inatividade e a latência dos aplicativos. Assim, não é necessário interagir com o AWS Support para ter benefícios de proteção contra DDoS. O AWS Shield Advanced está disponível para todos os clientes. No entanto, para entrar em contato com a equipe de resposta a DDoS, os clientes devem ter o Enterprise Support ou o Business Support do AWS Support.

O Amazon Chime é um serviço de comunicação que permite encontrar, conversar e realizar chamadas de negócios dentro e fora da sua organização, usando um só aplicativo. É um serviço de comunicações com pagamento conforme o uso sem taxas adiantadas, compromissos ou contratos de longo prazo

Serviços da AWS, como o AWS Lambda e o Amazon RDS, podem ser categorizados como PaaS, pois a AWS opera a camada de infraestrutura, o sistema operacional e as plataformas. Os clientes só precisam acessar os endpoints para armazenar e recuperar dados. `Com os serviços PaaS, os clientes são responsáveis por gerenciar os dados, classificar os ativos e aplicar as permissões apropriadas. No entanto, esses serviços atuam mais como serviços gerenciados, com a AWS gerenciando uma parte maior dos requisitos de segurança. No caso desses serviços, a AWS se encarrega das tarefas básicas de segurança, como aplicação de patches em sistemas operacionais e bancos de dados, configuração de firewall e recuperação de desastres.`

---
---
# Atividade: Cenário 1/2


![[Pasted image 20240910145044.png]]
![[Pasted image 20240910145105.png]]
Considere o caso em que um cliente usa os serviços e recursos da AWS que são mostrados aqui. Quem é responsável pela manutenção da segurança? A AWS ou o cliente?

O cliente usa o Amazon Simple Storage Service (Amazon S3) para armazenar dados. O cliente configurou uma virtual private cloud (VPC) com a Amazon Virtual Private Cloud (Amazon VPC). A instância do EC2 e a instância de banco de dados Oracle que ele criou são executadas na VPC.

Neste exemplo, o cliente deve gerenciar o sistema operacional (SO) convidado que é executado na instância do EC2. Com o passar do tempo, o sistema operacional convidado precisará ser atualizado e receber a aplicação de patches de segurança. Além disso, qualquer software de aplicativo ou utilitário que o cliente instalou na instância do Amazon EC2 também deve passar por manutenção. O cliente é responsável pela configuração do firewall da AWS (ou grupo de segurança) aplicado à instância do Amazon EC2. O cliente também é responsável pelas configurações da VPC que especificam as condições de rede nas quais a instância do Amazon EC2 é executada. Essas tarefas são as mesmas tarefas de segurança que uma equipe de TI executaria, não importa onde seus servidores estivessem localizados.

A instância Oracle neste exemplo fornece um estudo de caso interessante em termos de responsabilidade da AWS ou do cliente. Se o banco de dados for executado em uma instância do EC2, será responsabilidade do cliente aplicar atualizações e patches de software da Oracle. No entanto, se o banco de dados for executado como uma instância do Amazon RDS, será responsabilidade da AWS aplicar atualizações e patches de software da Oracle. Como o Amazon RDS é uma oferta de banco de dados gerenciada, as tarefas demoradas de administração de banco de dados (que incluem provisionamento, backups, aplicação de patches de software, monitoramento e escalabilidade de hardware) são processadas pela AWS. Para saber mais, consulte [Melhores práticas para a execução de bancos de dados Oracle na AWS](https://docs.aws.amazon.com/whitepapers/latest/oracle-database-aws-best-practices/introduction.html) e veja os detalhes.

# Atividade: Cenário 2/2
![[Pasted image 20240910145512.png]]
Agora, considere esse caso adicional em que um cliente usa os serviços e recursos da AWS que são mostrados aqui. Quem é responsável pela manutenção da segurança? A AWS ou o cliente?

Um cliente usa o Amazon S3 para armazenar dados. Ele configurou uma virtual private cloud (VPC) com a Amazon VPC e está executando um servidor Web em uma instância do EC2 na VPC. O cliente configurou um gateway da Internet como parte da VPC para que o servidor Web possa ser acessado com o uso do Console de Gerenciamento da AWS ou da Interface da Linha de Comando da AWS (CLI da AWS). Quando o cliente usa a CLI da AWS, a conexão requer o uso de chaves Secure Shell (SSH).

#ResumoSeção1Mod3
- A AWS e o cliente compartilham responsabilidades de segurança:
	- A AWS é responsável pela segurança da nuvem
	- O cliente é responsável pela segurança na nuvem

- A AWS é responsável por proteger a infraestrutura que executa os serviços de nuvem AWS, incluindo hardware, software, redes e instalações

- Para serviços categorizados como infraestrutura como serviço (IaaS), o cliente é responsável por executar as tarefas necessárias de configuraçãoe gerenciamento de segurança
	- Por exemplo, configurações do grupo de segurança, firewall e patches de segurança e atualizações de sistema operacional convidado
