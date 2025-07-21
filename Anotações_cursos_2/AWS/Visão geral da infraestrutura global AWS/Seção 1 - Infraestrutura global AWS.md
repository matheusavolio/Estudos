•A infraestrutura global da AWS foi projetada e criada para oferecer um ambiente de computação em nuvem flexível, confiável, escalável, e seguro com desempenho de rede global de alta qualidade.

•Este mapa de [https://infrastructure.aws](https://infrastructure.aws/) mostra as regiões atuais da AWS e outras que serão disponibilizados em breve.
![[Pasted image 20240909170806.png]]

O diagrama mostra as 22 regiões atuais da AWS, bem como algumas regiões que serão disponibilizadas em breve, incluindo Milão, Cidade do Cabo e Indonésia (a partir de outubro de 2019).

---
---
#### Regiões AWS
•Uma região da AWS é uma área geográfica.

•A replicação de dados entre regiões é controlada por você.

•A comunicação entre regiões usa a infraestrutura de rede backbone da AWS.

•Cada região fornece redundância total e conectividade com a rede.

•Uma região normalmente consiste em duas ou mais zonas de disponibilidade.

A infraestrutura da Nuvem AWS é criada em torno das regiões. A AWS tem 22 regiões em todo o mundo. Uma região da AWS é uma localização geográfica física com uma ou mais zonas de disponibilidade. As zonas de disponibilidade, por sua vez, consistem em um ou mais datacenters.

Para alcançar tolerância a falhas e estabilidade, as regiões são isoladas umas das outras. Os recursos em uma região não são replicados automaticamente para outras regiões. Quando você armazena dados em uma região específica, eles não são replicados fora dessa região.

É sua responsabilidade replicar dados entre regiões, se suas necessidades empresariais exigirem isso.

As regiões da AWS que foram introduzidas antes de 20 de março de 2019 são habilitadas por padrão. As regiões que foram introduzidas após 20 de março de 2019, como Ásia-Pacífico (Hong Kong) e Oriente Médio (Bahrein), são desabilitadas por padrão. É necessário habilitar essas regiões para que você possa usá-las. Você pode usar o Console de Gerenciamento da AWS para habilitar ou desabilitar uma região.

Algumas regiões têm acesso restrito. Uma conta da Amazon AWS (China) fornece acesso somente às regiões de Pequim e Ningxia. Para saber mais sobre a AWS na China, consulte: https://www.amazonaws.cn/en/about-aws/china/. A região isolada AWS GovCloud (EUA) foi projetada para permitir que clientes e órgãos governamentais dos EUA transfiram cargas de trabalho confidenciais para a nuvem, cumprindo seus requisitos específicos normativos e de conformidade.

---
---
#### Seleção de região

![[Pasted image 20240909171016.png]]
Há alguns fatores que você deve considerar ao selecionar a região ou regiões ideais onde você armazena dados e usa os serviços da AWS.

Uma consideração essencial é a governança de dados e os requisitos legais. As leis locais podem exigir que determinadas informações sejam mantidas dentro de limites geográficos. Essas leis podem restringir as regiões onde você pode oferecer conteúdo ou serviços. Por exemplo, considere a Diretiva de proteção de dados da União Europeia (UE).

Ao mesmo tempo, geralmente é desejável executar seus aplicativos e armazenar seus dados em uma região que esteja o mais próxima possível do usuário e dos sistemas que os acessarão. Isso ajudará você a reduzir a latência. O CloudPing é um site que você pode usar para testar a latência entre sua localização e todas as regiões da AWS. Para saber mais sobre o CloudPing, consulte: [http://www.cloudping.info/](http://www.cloudping.info/)

Lembre-se de que nem todos os serviços da estão disponíveis em todas as regiões. Para saber mais, consulte: [https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/?p=tgi&loc=4](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/?p=tgi&loc=4).

Por fim, há alguma variação no custo da execução de serviços, que pode depender da região escolhida. Por exemplo, a partir deste texto, a execução de uma instância Linux do Amazon Elastic Compute Cloud (Amazon EC2) sob demanda t3.medium na região Leste dos EUA (Ohio) custa 0,0416 USD por hora, mas a execução da mesma instância na região Ásia-Pacífico (Tóquio) custa 0,0544 USD por hora.

---
---
#### Zonas de disponibilidade
•Cada região tem várias zonas de disponibilidade. 

•Cada zona de disponibilidade é uma partição totalmente isolada da infraestrutura da AWS.

•No momento, existem 69 zonas de disponibilidade em todo o mundo

•As zonas de disponibilidade consistem em datacenters distintos

•Elas são projetadas para isolamento de falhas

•Elas são interconectadas a outras zonas de disponibilidade usando redes privadas de alta velocidade

•Você escolhe suas zonas de disponibilidade.

A AWS recomenda a replicação de dados e recursos entre zonas de disponibilidade para fins de resiliência.

![[Pasted image 20240909171201.png]]

Cada região da AWS contém vários locais isolados, conhecidos como zonas de disponibilidade.

Cada zona de disponibilidade oferece a capacidade de operar aplicativos e bancos de dados mais altamente disponíveis, tolerantes a falhas e escaláveis do que seria possível em um único datacenter. Cada zona de disponibilidade pode incluir vários datacenters (normalmente três) e, em grande escala, eles podem incluir centenas de milhares de servidores. Elas são partições totalmente isoladas da infraestrutura global da AWS. As zonas de disponibilidade têm sua própria infraestrutura de energia e são fisicamente separadas por muitos quilômetros de outras zonas de disponibilidade, embora todas as zonas de disponibilidade estejam a 100 km umas das outras.  

Todas as zonas de disponibilidade são interconectadas com redes de alta largura de banda e baixa latência por meio de fibra dedicada totalmente redundante que fornece alta vazão entre as zonas de disponibilidade. A rede realiza a replicação síncrona entre zonas de disponibilidade.

As zonas de disponibilidade ajudam a criar aplicativos altamente disponíveis. Quando um aplicativo é particionado entre zonas de disponibilidade, as empresas ficam melhor isoladas e protegidas contra problemas como relâmpagos, tornados, terremotos e muito mais.

Você é responsável por selecionar as zonas de disponibilidade onde seus sistemas residirão. Os sistemas podem abranger várias zonas de disponibilidade. A AWS recomenda a replicação entre zonas de disponibilidade para fins de resiliência. Você deve projetar os sistemas para sobreviverem a uma falha temporária ou prolongada de uma zona de disponibilidade se ocorrer um desastre.

---
---
#### Datacenters AWS
•Os datacenters da AWS são projetados para segurança.

•Os datacenters são onde os dados residem e o processamento de dados ocorre.

•Cada datacenter tem energia, redes e conectividade redundantes e está hospedado em uma instalação separada.

Normalmente, um datacenter tem de 50.000 a 80.000 servidores físicos

A base da infraestrutura da AWS são os datacenters. Os clientes não especificam um datacenter para a implantação de recursos. Em vez disso, uma zona de disponibilidade é o nível de especificação mais granular que um cliente pode fazer. No entanto, um datacenter é o local onde os dados reais residem. A Amazon opera datacenters de última geração e altamente disponíveis. Embora sejam raras, podem ocorrer falhas que afetam a disponibilidade das instâncias no mesmo local. Se você hospedar todas as suas instâncias em um único local afetado por tal falha, nenhuma delas ficará disponível.

Os datacenters são projetados com segurança, com vários fatores em mente:

•Cada local é cuidadosamente avaliado para mitigar os riscos ambientais.

•Os datacenters têm um design redundante que prevê e tolera falhas enquanto mantém os níveis de serviço.

•Para garantir a disponibilidade, o backup de componentes essenciais do sistema é feito em várias zonas de disponibilidade.

•A AWS monitora continuamente o uso dos serviços para implantar uma infraestrutura que ofereça suporte aos nossos compromissos e requisitos de disponibilidade.

•Os locais dos datacenters não são divulgados e todo o acesso a eles é restrito.

•Em caso de falha, processos automatizados desviam o tráfego de dados da área afetada.

A AWS usa equipamentos de rede personalizados originados de vários fabricantes de dispositivos originais (ODMs). Os ODMs projetam e fabricam produtos com base nas especificações de uma segunda empresa. Em seguida, a segunda empresa remarca os produtos para venda.

---
---

#### Pontos de presença 
•A AWS fornece uma rede global de 187 pontos de presença  

•Consiste em 176 pontos de presença e 11 pontos de presença de caches regionais

•Usada com o Amazon CloudFront

•Uma Content Delivery Network  
(CDN - Rede de entrega de conteúdo) global que entrega conteúdo aos usuários finais com latência reduzida

Os pontos de presença decaches regionais usados para conteúdo com acesso pouco frequente

O Amazon CloudFront é uma rede de entrega de conteúdo (CDN) usada para distribuir conteúdo aos usuários finais para reduzir a latência. O Amazon Route 53 é um serviço de Domain Name System (DNS). As solicitações enviadas para qualquer um desses serviços serão roteadas automaticamente para o ponto de presença mais próximo para diminuir a latência.

Os pontos de presença da AWS estão localizados na maioria das principais cidades (69 cidades no total) de 30 países em todo o mundo. Ao medir continuamente a conectividade, a performance e a computação com a Internet para encontrar a melhor maneira de rotear solicitações, os pontos de presença oferecem uma melhor experiência de usuário quase em tempo real. Eles são usados por muitos serviços da AWS, incluindo os serviços Amazon CloudFront, Amazon Route 53, AWS Shield e AWS Web Application Firewall (AWS WAF).

Os caches de borda regionais são usados por padrão com o Amazon CloudFront. Os pontos de presença de caches regionais são usados quando você tem conteúdo que não é acessado com frequência suficiente para permanecer em um ponto de presença. Os pontos de cache regional absorvem esse conteúdo e fornecem uma alternativa para obter esse conteúdo no servidor de origem.

---
---
#### Recursos de infraestrutura da AWS
•Elasticidade e escalabilidade

•Infraestrutura elástica; adaptação dinâmica da capacidade

•Infraestrutura escalável; adapta-se para acomodar o crescimento

•Tolerância a falhas

•Continua funcionando corretamente na presença de uma falha

•Redundância integrada de componentes

•Alta disponibilidade

•Alto nível de desempenho operacional

•Tempo de inatividade mínimo

•Sem intervenção humana

Agora que você tem uma boa compreensão dos principais componentes que compõem a infraestrutura global da AWS, vamos considerar os benefícios oferecidos por essa infraestrutura.

A infraestrutura global da AWS tem vários recursos valiosos:

- Primeiro, ele é elástico e escalável. Isso significa que os recursos podem se ajustar dinamicamente para aumentos ou diminuições nos requisitos de capacidade. Ele também pode se ajustar rapidamente para acomodar o crescimento.

- Segundo, essa infraestrutura é tolerante a falhas, o que significa que ela tem redundância de componente integrada que permite continuar as operações apesar de um componente com falha.

- Por fim, ele requer intervenção mínima ou nenhuma intervenção humana, enquanto fornece alta disponibilidade com tempo de inatividade mínimo.

---
---
#### #ResumoSeção1Mod2

•A infraestrutura global da AWS consiste em regiões e zonas de disponibilidade.

•Normalmente, a escolha de uma região é baseada em requisitos de conformidade ou para reduzir a latência.

•Cada zona de disponibilidade é fisicamente separada de outras zonas de disponibilidade e tem alimentação, redes e conectividade redundantes.

•Os pontos de presença e os pontos de presença de caches regionais melhoram a performance armazenando conteúdo em cache mais próximo dos usuários.
