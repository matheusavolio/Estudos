Este módulo aborda os seguintes tópicos:

	•Introdução à computação em nuvem

	•Vantagens da computação em nuvem

	•Introdução à Amazon Web Services (AWS)

	•AWS Cloud Adoption Framework (AWS CAF)

Por fim, você deverá concluir um teste de conhecimento que será usado para testar sua compreensão dos principais conceitos abordados neste módulo

#### Definição de computação em nuvem
`Computação em nuvem` é a entrega sob demanda de poder computacional, banco de dados, armazenamento, aplicativos e outros recursos de TI pela Internet com uma definição de preço conforme o uso. Esses recursos são executados em computadores servidores localizados em grandes datacenters em todo o mundo. Quando você usa um provedor de serviços em nuvem como a AWS, ele é o proprietário dos computadores que você está usando. Esses recursos podem ser usados em conjunto, como componentes básicos, para criar soluções que ajudam a cumprir metas de negócios e requisitos de tecnologia.

## Infraestrutura como software
A computação em nuvem permite que você deixe de pensar em sua infraestrutura como hardware e passe a pensar nela (e usá-la) como software. Mas o que isso significa?

#### Modelo de computação tradicional:
	•Infraestrutura como hardware

	•Soluções de hardware:

	•Exigem espaço, equipe, segurança física, planejamento, despesas de capital

	•Têm um ciclo longo de aquisição de hardware

	•Exigem provisionamento de capacidade por meio da tentativa de adivinhar os picos         máximos teóricos

No modelo de computação tradicional, considera-se que a infraestrutura é composta por hardware. As soluções de hardware são físicas, o que significa que exigem espaço, equipe, segurança física, planejamento e despesas de capital.

Além de um investimento inicial significativo, outro aspecto impeditivo da computação tradicional é o ciclo longo de aquisição de hardware que envolve a aquisição, o provisionamento e a manutenção de infraestrutura local.

Com uma solução de hardware, você precisa se perguntar se há capacidade de recursos ou armazenamento suficiente para atender às suas necessidades e então provisionar capacidade tentando adivinhar os picos máximos teóricos. Se você não atingir o pico máximo projetado, pagará pelos recursos caros que permanecerem ociosos. Se você exceder o pico máximo projetado, não terá capacidade suficiente para atender às suas necessidades. Se suas necessidades mudarem, você precisará gastar tempo, esforço e dinheiro para implementar uma nova solução.

Por exemplo, se você quisesse provisionar um novo site, precisaria comprar o hardware, montá-lo e empilhá-lo, colocá-lo em um datacenter e, em seguida, gerenciá-lo você mesmo ou escolher alguém para fazer isso. Essa abordagem é cara e demorada.

#### Modelo de computação em nuvem
- Infraestrutura como software

- Soluções de software:

	- São flexíveis

	- Podem mudar com mais rapidez, facilidade e economia do que as soluções de hardware

	- Eliminam as tarefas monolíticas de trabalho pesado
Por outro lado, a computação em nuvem permite considerar que a infraestrutura é composta por software. As soluções de software são flexíveis. Você pode selecionar os serviços de nuvem que melhor atendam às suas necessidades, provisionar e encerrar esses recursos sob demanda e pagar pelo que usar. É possível aumentar e diminuir a escala de recursos de maneira elástica e automatizada. Com o modelo de computação em nuvem, você pode tratar os recursos como temporários e descartáveis. A flexibilidade oferecida pela computação em nuvem permite que as empresas implementem novas soluções rapidamente e com baixos custos iniciais.

Comparadas às soluções de hardware, as soluções de software podem mudar de maneira muito mais rápida, fácil e econômica

#### Modelos de serviço em nuvem
Existem três modelos principais de serviços em nuvem. Cada modelo representa uma parte diferente da pilha de computação em nuvem e oferece um nível diferente de controle sobre seus recursos de TI:
##### #IaaS:
- `Infraestrutura como serviço (IaaS): os serviços nesta categoria são os componentes básicos da TI em nuvem e, geralmente, fornecem acesso (virtual ou no hardware dedicado) a recursos de rede e computadores, bem como espaço para o armazenamento de dados. A IaaS oferece o mais alto nível de flexibilidade e controle de gerenciamento sobre seus recursos de TI. É o modelo mais semelhante aos recursos de TI existentes com os quais muitos departamentos e desenvolvedores de TI já estão familiarizados.
##### #PaaS
- `Plataforma como serviço (PaaS): os serviços nessa categoria reduzem a necessidade de gerenciar a infraestrutura subjacente (geralmente hardware e sistemas operacionais) e permitem que você se concentre na implantação e no gerenciamento de seus aplicativos.
##### #SaaS
- `Software como serviço (SaaS): os serviços nesta categoria fornecem um produto completo que o provedor de serviços executa e gerencia. Na maioria dos casos, o software como serviço refere-se a aplicativos de usuário final. Com uma oferta de SaaS, não é necessário pensar na manutenção do serviço ou no gerenciamento da infraestrutura subjacente. É necessário pensar apenas em como você planeja usar esse software específico. Um exemplo comum de aplicação do SaaS é o webmail, no qual você pode enviar e receber e-mails sem precisar gerenciar recursos adicionais para o produto de e-mail nem manter os servidores e sistemas operacionais no qual o programa de e-mail está sendo executado.

#### Modelo de implementação de computação em nuvem
Existem três modelos principais de implantação de computação em nuvem, que representam os ambientes de nuvem nos quais seus aplicativos podem ser implantados:
##### #Nuvem
- `Nuvem: um aplicativo baseado em nuvem é totalmente implantado na nuvem, e todas as partes do aplicativo são executadas na nuvem. Os aplicativos na nuvem foram criados na nuvem ou migraram de uma infraestrutura existente para aproveitar os [benefícios da computação em nuvem](https://aws.amazon.com/what-is-cloud-computing/?pg=TOCC). Os aplicativos baseados em nuvem podem ser criados com base em partes de infraestrutura de baixo nível ou podem usar serviços de nível superior que oferecem abstração dos requisitos de gerenciamento, arquitetura e escalabilidade da infraestrutura principal.

##### #Híbrida
- `Híbrida: uma implantação híbrida é uma maneira de conectar infraestrutura e aplicativos entre recursos baseados na nuvem e recursos atuais que não estão na nuvem. O método mais comum de implantação híbrida é entre a nuvem e a infraestrutura local existente. Esse modelo permite que uma organização amplie e expanda sua infraestrutura para a nuvem enquanto conecta recursos de nuvem a sistemas internos.

##### #NuvemPrivada
 - `No local: a implantação de recursos no local, usando ferramentas de gerenciamento de virtualização e recursos, às vezes é chamada de nuvem privada. A implantação no local não oferece muitos dos benefícios da computação em nuvem, mas, às vezes, é mais adequada devido à sua capacidade de oferecer [recursos dedicados](https://aws.amazon.com/enterprise/private/?pg=TOCC). Na maioria dos casos, este modelo de implantação é igual à infraestrutura de TI antiga, mas também pode usar tecnologias de gerenciamento e virtualização de aplicativos para aumentar a utilização de recursos.
#### Semelhança entre a AWS e a TI tradicional

Há muitas semelhanças entre a AWS e o espaço tradicional de TI local:

- `Os grupos de segurança da AWS, as listas de controle de acesso à rede (Network ACLs) e o AWS Identity and Access Management (IAM) são semelhantes a firewalls, listas de controle de acesso (ACLs) e administradores.

- `O Elastic Load Balancing e a Amazon Virtual Private Cloud (Amazon VPC) são semelhantes a roteadores, pipelines de rede e switches.

- `As instâncias de Imagens de máquina da Amazon (AMIs) e do Amazon Elastic Compute Cloud (Amazon EC2) são semelhantes aos servidores locais.

- `O Amazon Elastic Block Store (Amazon EBS), o Amazon Elastic File System (Amazon EFS), o Amazon Simple Storage Service (Amazon S3) e o Amazon Relational Database Service (Amazon RDS) são semelhantes ao armazenamento de conexão direta (DAS), redes de área de armazenamento (SAN), armazenamento conectado à rede (NAS) e um serviço de gerenciamento de banco de dados relacional (RDBMS).

Com os serviços e recursos da AWS, você pode fazer quase tudo o que deseja com um datacenter tradicional

#### #ResumoSeção1Mod1
Algumas das principais lições desta seção do módulo são:

- `O termo “computação em nuvem” se refere à entrega de recursos de TI sob demanda por meio da Internet, com pagamento conforme o uso.

- `A computação em nuvem permite pensar em sua infraestrutura (e usá-la) como software.

- `Existem três modelos de serviços em nuvem: IaaS, PaaS e SaaS.

- `Existem três modelos de implantação em nuvem: nuvem, híbrida e no local (ou nuvem privada).

Existem muitos serviços parecidos com os da AWS para o espaço de TI tradicional, no local
