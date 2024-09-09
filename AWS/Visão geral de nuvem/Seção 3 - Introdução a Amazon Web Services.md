Em geral, um serviço web é qualquer software disponibilizado pela Internet ou em redes privadas (intranet). Um serviço web usa um formato padronizado, como Extensible Markup Language (XML) ou JavaScript Object Notation (JSON), para a solicitação e a resposta de uma interação de interface de programação de aplicativos (API). Ele não está vinculado a nenhum sistema operacional ou linguagem de programação. Ele é autodescritivo por meio de um arquivo de definição de interface e é detectável.

---
---

A Amazon Web Services (AWS) é uma plataforma de nuvem segura que oferece um amplo conjunto de produtos globais baseados na nuvem. Como esses produtos são entregues pela Internet, você tem acesso sob demanda aos recursos de computação, armazenamento, rede, banco de dados e outros recursos de TI que podem ser necessários para seus projetos, bem como às ferramentas para gerenciá-los. É possível provisionar e executar imediatamente os recursos da AWS. Os recursos ficam prontos para uso em minutos.

---
---

A AWS oferece flexibilidade. Seu ambiente da AWS pode ser reconfigurado e atualizado sob demanda e sua escala pode ser aumentada ou reduzida automaticamente para atender aos padrões de uso e otimizar gastos, ou o ambiente pode ser encerrado temporariamente ou permanentemente. O faturamento dos serviços da AWS deixa de ser uma despesa de capital e torna-se uma despesa operacional.

Os serviços da AWS são projetados para funcionar juntos e oferecer suporte a praticamente qualquer tipo de aplicativo ou carga de trabalho. Pense nesses serviços como blocos fundamentais, que você pode montar rapidamente para criar soluções sofisticadas e escaláveis e, em seguida, ajustá-las à medida que suas necessidades mudarem.

---
---
Por exemplo, digamos que você esteja criando um aplicativo de banco de dados. Seus clientes podem estar enviando dados para suas instâncias do Amazon Elastic Compute Cloud (Amazon EC2), que é um serviço na categoria de computação. Esses servidores EC2 agrupam os dados em lotes em incrementos de um minuto e adicionam um objeto por cliente ao Amazon Simple Storage Service (Amazon S3), o serviço de armazenamento da AWS que você escolheu usar. Em seguida, você pode usar um banco de dados não relacional, como o Amazon DynamoDB, para potencializar seu aplicativo, por exemplo, para criar um índice que permita encontrar todos os objetos de determinado cliente que foram coletados durante determinado período. É possível executar esses serviços dentro de uma Amazon Virtual Private Cloud (Amazon VPC), que é um serviço na categoria de rede.

O objetivo deste exemplo simples é ilustrar a possibilidade de selecionar serviços web de diferentes categorias e usá-los juntos para criar uma solução (neste caso, um aplicativo de banco de dados). Naturalmente, as soluções criadas podem ser bastante complexas.

---
---
A escolha do serviço dependerá dos objetivos empresariais e dos requisitos de tecnologia. No exemplo que acabamos de ver, a solução usou o Amazon EC2 como o serviço de computação. No entanto, esse é apenas um dos muitos serviços de computação que a AWS oferece. Veja a seguir outras ofertas de computação da AWS que você pode usar para os seguintes exemplos de casos de uso:

•[Amazon EC2](https://aws.amazon.com/ec2/): você quer controle total sobre seus recursos de computação da AWS.

•[AWS Lambda](https://aws.amazon.com/lambda/): você deseja executar seu código e não gerenciar ou provisionar servidores.

•[AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/): você quer um serviço que implante, gerencie e escale seus aplicativos web para você.

•[Amazon Lightsail](https://aws.amazon.com/lightsail/): você precisa de uma plataforma em nuvem leve para um aplicativo web simples.

•[AWS Batch](https://aws.amazon.com/batch/): você precisa executar centenas de milhares de cargas de trabalho em lote.

•[AWS Outposts](https://aws.amazon.com/outposts/): você deseja executar a infraestrutura da AWS em seu datacenter local.

•[Amazon Elastic Container Service](https://aws.amazon.com/ecs/) (Amazon ECS), [Amazon Elastic Kubernetes Service](https://aws.amazon.com/eks/) (Amazon EKS) ou [AWS Fargate](https://aws.amazon.com/fargate/): você deseja implementar uma arquitetura de contêineres ou microsserviços.

•[VMware Cloud on AWS](https://aws.amazon.com/vmware/): você tem uma plataforma de virtualização de servidor local que deseja migrar para a AWS.

Da mesma forma, há uma variedade de serviços para você escolher nas outras categorias, e o número de ofertas continua crescendo.

---
---

A variedade de serviços da AWS pode ser intimidadora no início da jornada para a nuvem. Este curso se concentra em alguns dos serviços mais comuns nas seguintes categorias de serviço: computação, armazenamento, banco de dados, entrega de redes e conteúdo, segurança, identidade e conformidade, gerenciamento e governança e gerenciamento de custos da AWS.

•Amazon Elastic Block Store (Amazon EBS)
•Amazon Elastic Compute Cloud (Amazon EC2)
•Amazon Elastic Container Registry (Amazon ECR)
•Amazon Elastic Container Service (Amazon ECS)
•Amazon Elastic File System (Amazon EFS)
•Amazon Elastic Kubernetes Service (Amazon EKS)
•Amazon Relational Database Service (Amazon RDS)
•Amazon Simple Storage Service (Amazon S3)
•Amazon Virtual Private Cloud (Amazon VPC)
•AWS Identity and Access Management (IAM)
•AWS Key Management Service (AWS KMS)

---
---
Talvez você esteja se perguntando como acessar a ampla variedade de serviços oferecidos pela AWS. Há três maneiras de criar e gerenciar recursos na Nuvem AWS:

•Console de Gerenciamento da AWS: o console fornece uma interface gráfica avançada para a maioria dos recursos oferecidos pela AWS. (Observação: às vezes os recursos novos ainda não têm todas as capacidades embutidas no console na data de lançamento).

•Interface da linha de comando da AWS (CLI da AWS): a CLI da AWS fornece um conjunto de utilitários que podem ser executados a partir de um script de comando no Linux, macOS ou Microsoft Windows.

•Software Development Kits (SDKs): a AWS fornece pacotes que permitem acessar a AWS em uma variedade de linguagens de programação populares. Isso facilita o uso da AWS em seus aplicativos existentes e permite a criação de aplicativos para implantar e monitorar sistemas complexos inteiramente por meio de código.

As três opções são criadas em uma API semelhante à REST comum que serve como base da AWS.

Para saber mais sobre as ferramentas que você pode usar para desenvolver e gerenciar aplicativos na AWS, consulte [Ferramentas para criar na AWS](https://aws.amazon.com/tools/).

---
---
