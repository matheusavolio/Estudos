# AWS Identity and Access Management (IAM)

- Use o IAM para gerenciar o acesso aos recursos da AWS 
	- Um recurso é uma entidade em uma conta da AWS com a qual você pode trabalhar
	- Exemplo de recursos: uma instância do Amazon EC2 ou um bucket do Amazon S3

- Exemplo: controle quem pode encerrar instâncias do Amazon EC2
- Defina direitos de acesso refinados 
	- Quem pode acessar o recurso
	- Quais recursos podem ser acessados e o que o usuário pode fazer com o recurso
	- Como os recursos podem ser acessados
- O IAM é um recurso de conta da AWS gratuito

O AWS Identity and Access Management (IAM) permite controlar o acesso a serviços de computação, armazenamento, banco de dados e aplicativos na Nuvem AWS. O IAM pode ser usado para lidar com autenticação e para especificar e aplicar políticas de autorização para que você possa especificar quais usuários podem acessar quais serviços.

`O IAM é uma ferramenta que gerencia de maneira centralizada o acesso à execução, configuração, gerenciamento e encerramento de recursos em sua conta da AWS. Ele fornece controle granular sobre o acesso a recursos, incluindo a capacidade de especificar exatamente quais chamadas de API o usuário está autorizado a fazer para cada serviço. Independentemente de você usar o Console de Gerenciamento da AWS, a CLI da AWS ou os kits de desenvolvimento de software (SDKs) da AWS, cada chamada para um serviço da AWS é uma chamada de API.
`
Com o IAM, você pode gerenciar quais recursos podem ser acessados por quem e como esses recursos podem ser acessados. Você pode conceder permissões diferentes a pessoas distintas para recursos variados. Por exemplo, você pode permitir a alguns usuários acesso total ao Amazon EC2, Amazon S3, Amazon DynamoDB, Amazon Redshift e outros serviços da AWS. No entanto, para outros usuários, pode permitir acesso somente leitura a apenas alguns buckets do S3. Da mesma forma, pode conceder permissão a outros usuários para administrar apenas instâncias do EC2 específicas. Também é possível permitir que alguns usuários acessem apenas as informações de faturamento da conta, mas nada mais.

O IAM é um recurso da sua conta da AWS que é oferecido gratuitamente.

---
---

# IAM: Componentes essenciais

![[Pasted image 20240910151142.png]]
Para entender como usar o IAM para proteger sua conta da AWS, é importante compreender o papel e a função de cada um dos quatro componentes do IAM.

Um usuário do IAM é uma pessoa ou aplicativo definido em uma conta da AWS e que deve fazer chamadas de API para produtos da AWS. Cada usuário deve ter um nome exclusivo (sem espaços no nome) na conta da AWS e um conjunto de credenciais de segurança que não seja compartilhado com outros usuários. Essas credenciais são diferentes das credenciais de segurança do usuário raiz da conta da AWS. Cada usuário é definido em uma única conta da AWS.

Um grupo do IAM é um conjunto de usuários do IAM. Você pode usar grupos do IAM para simplificar a especificação e o gerenciamento de permissões para vários usuários.

Uma política do IAM é um documento que define permissões para determinar o que os usuários podem fazer na conta da AWS. Uma política normalmente concede acesso a recursos específicos e especifica o que o usuário pode fazer com esses recursos. As políticas também podem negar explicitamente o acesso.

Uma função do IAM é uma ferramenta para conceder acesso temporário a recursos específicos da AWS em uma conta da AWS.

---
---
#### Autenticar como um usuário do IAM para obter acesso

Ao definir um usuário do IAM, você seleciona os tipos de acesso que o usuário tem permissão para usar.

- Acesso programático
	- Autentique usando:
		- ID da chave de acesso
		- Chave de acesso secreta
- Fornece acesso à CLI e ao SDK da AWS

- Acesso ao Console de Gerenciamento da AWS
	- Autentique usando:
		 - ID ou alias da conta com 12 dígitos
		- Nome de usuário do IAM
		- Senha do IAM
	- Se ativada, a Multi-Factor Authentication (MFA) solicita um código de autenticação.

![[Pasted image 20240910152046.png]]
Autenticação é um conceito básico de segurança da computação: um usuário ou sistema deve primeiro comprovar a identidade. Considere como você se autentica quando vai para o aeroporto e quer passar pela segurança do aeroporto para poder pegar um voo. Nessa situação, você deve apresentar algum tipo de identificação ao oficial de segurança para comprovar sua identidade antes de entrar em uma área restrita. Um conceito semelhante se aplica para a obtenção de acesso aos recursos da AWS na nuvem.  

Ao definir um usuário do IAM, você seleciona o tipo de acesso que o usuário tem permissão para usar para acessar os recursos da AWS. Você pode atribuir dois tipos diferentes de acesso aos usuários: acesso programático e acesso ao Console de Gerenciamento da AWS. Também pode atribuir somente acesso programático, somente acesso ao console ou ambos.

Se você conceder acesso programático, o usuário do IAM precisará apresentar um ID de chave de acesso e uma chave de acesso secreta ao fazer uma chamada de API da AWS usando a CLI da AWS, o SDK da AWS ou alguma outra ferramenta de desenvolvimento.

Se você conceder acesso ao Console de Gerenciamento da AWS, o usuário do IAM deverá preencher os campos que aparecem na janela de login do navegador. O usuário deve fornecer o ID da conta com 12 dígitos ou o alias da conta correspondente. O usuário também deve inserir o nome de usuário e a senha do IAM. Se a Multi-Factor Authentication (MFA) estiver habilitada para o usuário, ele também deverá fornecer um código de autenticação.

---
---

#### Autorização: quais ações são permitidas
![[Pasted image 20240910152346.png]]
Autorização é o processo de determinar quais permissões um usuário, serviço ou aplicativo deve receber. Depois que um usuário for autenticado, ele deverá ser autorizado a acessar os serviços da AWS.

Por padrão, os usuários do IAM não têm permissões para acessar nenhum recurso ou dados em uma conta da AWS. Em vez disso, você deve conceder permissões explicitamente a um usuário, grupo ou função por meio da criação de uma política, que é um documento no formato JavaScript Object Notation (JSON). Uma política lista permissões que permitem ou negam acesso a recursos na conta da AWS.

---
---
#### IAM: autorização
- Atribua permissões criando uma política do IAM.
- As permissões determinam quais recursos e operações são permitidos:
	- Todas as permissões são implicitamente negadas por padrão.
	- Se algo for explicitamente negado, nunca será permitido.

Prática recomendada: siga o princípio do privilégio mínimo.

**Observação**: o escopo das configurações de serviço do IAM é global. As configurações se aplicam a todas as regiões da AWS.

Para atribuir permissão a um usuário, grupo ou função, você deve criar uma política do IAM (ou encontrar uma política existente na conta). Não há permissões padrão. Todas as ações na conta são negadas ao usuário por padrão (negação implícita), a menos que elas sejam explicitamente permitidas. Qualquer ação que você não permita explicitamente é negada. Todas as ações que você negar explicitamente serão sempre negadas.

`O princípio do privilégio mínimo` é um conceito importante na segurança da computação. Ele consiste em conceder apenas os privilégios mínimos necessários para o usuário, de acordo com as necessidades de seus usuários. Ao criar políticas do IAM, é uma prática recomendada seguir essa orientação de segurança de concessão de privilégio mínimo. Determine o que os usuários precisam fazer e, em seguida, crie políticas para eles que permitam que eles executem apenas essas tarefas. Comece com um conjunto mínimo de permissões e conceda permissões adicionais conforme necessário. Isso é mais seguro do que começar com permissões muito amplas e depois tentar bloquear as permissões concedidas.

O escopo das configurações de serviço do IAM é global. As configurações não são definidas no nível da região da AWS. As configurações do IAM se aplicam a todas as regiões da AWS.

---
---
#### Políticas do IAM


![[Pasted image 20240910152827.png]]
- Uma política do IAM é um documento que define permissões
	- Habilita um controle de acesso refinado
- Dois tipos de políticas: baseadas em identidade e em recurso
- Políticas baseadas em identidade 
	- Anexe uma política a qualquer entidade do IAM
		- Um usuário do IAM, um grupo do IAM ou uma função do IAM
	- As políticas especificam:
		- Ações que podem ser executadas pela entidade
		- Ações que não podem ser executadas pela entidade
	- Uma única política pode ser anexada a várias entidades
	- Uma única entidade pode ter várias políticas anexadas a ela
- Políticas baseadas em recursos
	- Anexadas a um recurso (como um bucket do S3)


Uma política do IAM é uma declaração formal de permissões que serão concedidas a uma entidade. As políticas podem ser anexadas a qualquer entidade do IAM. As entidades incluem usuários, grupos, funções ou recursos. Por exemplo, você pode anexar uma política aos recursos da AWS que bloquearão todas as solicitações que não vierem de um intervalo de endereços IP (Internet Protocol) aprovado. As políticas especificam quais ações são permitidas, em quais recursos permitir as ações e qual será o efeito quando o usuário solicitar acesso aos recursos.

A ordem em que as políticas são avaliadas não tem efeito no resultado da avaliação. Todas as políticas são avaliadas, e o resultado é sempre que a solicitação é permitida ou negada. Quando há um conflito, a política mais restritiva se aplica.

Há dois tipos de políticas do IAM. As políticas baseadas em identidade são políticas de permissões que você pode anexar a uma entidade principal (ou identidade), como um usuário, função ou grupo do IAM. Essas políticas controlam quais ações essa identidade pode realizar, em quais recursos e em que condições. As políticas baseadas em identidade podem ser categorizadas como:

- `Políticas gerenciadas`: políticas independentes baseadas em identidade que você pode anexar a vários usuários, grupos e funções em sua conta da AWS

- `Políticas em linha`: políticas que você cria e gerencia e que são incorporadas diretamente em um único usuário, grupo ou função.


As `políticas baseadas em recursos` são documentos de política JSON que você anexa a um recurso, como um bucket do S3. Essas políticas controlam quais ações uma entidade principal pode realizar nesse recurso e em que condições.

#### Exemplo de política do IAM

![[Pasted image 20240910153635.png]]
Como mencionado anteriormente, os documentos de política do IAM são escritos em JSON.
O exemplo de política do IAM concede aos usuários acesso apenas aos seguintes recursos:

- A tabela do DynamoDB cujo nome é representado por table-name.
- O bucket do S3 da conta da AWS, cujo nome é representado por bucket-name, e todos os objetos que ela contém.

A política do IAM também inclui um elemento de negação explícita ("Effect":"Deny"). O elemento NotResource ajuda a garantir que os usuários não possam usar nenhuma outra ação ou recurso do DynamoDB ou do S3, exceto os especificados na política, mesmo que as permissões tenham sido concedidas em outra política. Uma instrução de negação explícita tem precedência sobre uma instrução de permissão.

---
---

#### Políticas baseadas em recursos

![[Pasted image 20240910153844.png]]
Embora as políticas baseadas em identidade estejam anexadas a um usuário, um grupo ou uma função, as políticas baseadas em recursos são anexadas a um recurso, como um bucket do S3. Essas políticas especificam quem pode acessar o recurso e quais ações podem ser executadas nele.

As políticas baseadas em recursos são definidas somente em linha, o que significa que você define a política no próprio recurso, em vez de criar um documento de política do IAM separado que você anexa. Por exemplo, para criar uma política de bucket do S3 (um tipo de política baseada em recursos) em um bucket do S3, navegue até o bucket, clique na guia Permissions (Permissões), clique no botão Bucket Policy (Política de bucket) e defina o documento de política formatado em JSON. Uma lista de controle de acesso (ACL) do Amazon S3 é outro exemplo de uma política baseada em recursos.

O diagrama mostra duas maneiras diferentes de conceder ao usuário MaryMajor acesso a objetos no bucket do S3 chamado photos. À esquerda, você vê um exemplo de uma política baseada em identidade. Uma política do IAM que concede acesso ao bucket do S3 é anexada ao usuário MaryMajor. À direita, você vê um exemplo de uma política baseada em recursos. A política de bucket do S3 para o bucket photos especifica que o usuário MaryMajor tem permissão para listar e ler os objetos no bucket.

Você pode definir uma instrução de negação em uma política de bucket para restringir o acesso a usuários específicos do IAM, mesmo que os usuários tenham acesso em uma política separada baseada em identidade. Uma instrução de negação explícita sempre terá precedência sobre qualquer instrução de permissão.

---
---

#### Permissões do IAM:

![[Pasted image 20240910153929.png]]
As políticas do IAM permitem ajustar privilégios que são concedidos a usuários, grupos e funções do IAM.

Quando o IAM determina se uma permissão é permitida, ele primeiro verifica a existência de qualquer política de negação explícita aplicável. Se não houver uma negação explícita, ele verificará se há alguma política de permissão explícita aplicável. Se não houver uma política de negação explícita nem uma de permissão explícita, o IAM reverterá para o padrão, que é negar o acesso. Esse processo é chamado de negação implícita. O usuário terá permissão para realizar a ação somente se a ação solicitada não for explicitamente negada e for explicitamente permitida.

Pode ser difícil descobrir se o acesso a um recurso será concedido a uma entidade do IAM quando você desenvolver políticas do IAM. O [Simulador de políticas do IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) é uma ferramenta útil para testar e solucionar problemas de políticas do IAM.

---
---

#### Grupos do IAM
![[Pasted image 20240910154009.png]]
Um grupo do IAM é um conjunto de usuários do IAM. Os grupos do IAM oferecem uma maneira prática de especificar permissões para um conjunto de usuários, o que pode facilitar o gerenciamento das permissões para esses usuários.

Por exemplo, você pode criar um grupo do IAM chamado Desenvolvedores e anexar uma ou várias políticas do IAM a esse grupo que concedem as permissões de acesso a recursos da AWS de que os desenvolvedores geralmente precisam. Qualquer usuário que você adicionar ao grupo Desenvolvedores terá automaticamente as permissões atribuídas ao grupo. Nesse caso, você não precisa anexar as políticas do IAM diretamente ao usuário. Se um novo usuário ingressa em sua organização e precisa receber privilégios de desenvolvedor, você pode simplesmente adicioná-lo ao grupo Desenvolvedores. Da mesma forma, se uma pessoa muda de função em sua organização, em vez de editar as permissões desse usuário, basta removê-lo do grupo.

Características importantes dos grupos do IAM:

•Um grupo pode conter vários usuários, e um usuário pode pertencer a vários grupos.

•Os grupos não podem ser aninhados. Um grupo pode conter apenas usuários, não outros grupos.

•Não há um grupo padrão que inclua automaticamente todos os usuários na conta da AWS. Se você quiser ter um grupo com todos os usuários da conta, precisará criar o grupo e adicionar cada novo usuário a ele.

---
---
#### Funções do IAM:

![[Pasted image 20240910154038.png]]
Uma função do IAM é uma identidade do IAM que você pode criar em sua conta que tenha permissões específicas. Uma função do IAM é semelhante a um usuário do IAM porque também é uma identidade da AWS à qual você pode anexar políticas de permissões, e essas permissões determinam o que a identidade pode e não pode fazer na AWS. No entanto, em vez de ser exclusivamente associada a uma pessoa, uma função destina-se a ser assumida por qualquer pessoa que precisar. Além disso, uma função não tem credenciais de longo prazo padrão, como uma senha ou chaves de acesso, associadas a ela. Em vez disso, quando você assume uma função, ela fornece credenciais de segurança temporárias para a sessão da função.

Você pode usar funções para delegar acesso a usuários, aplicativos ou serviços que normalmente não têm acesso aos seus recursos da AWS. Por exemplo, você pode conceder aos usuários em sua conta da AWS acesso a recursos que normalmente eles não têm ou conceder aos usuários em uma conta da AWS acesso a recursos em outra conta. Também pode permitir que um aplicativo móvel use recursos da AWS, mas não incorporar chaves da AWS no aplicativo (quando for difícil alterá-las e quando os usuários poderão extraí-las e usá-las indevidamente). Além disso, às vezes você deseja conceder acesso à AWS a usuários que já têm identidades definidas fora da AWS, como no diretório corporativo. Você também pode conceder acesso à sua conta a terceiros, para que eles possam realizar uma auditoria em seus recursos.

Para todos esses exemplos de casos de uso, as funções do IAM são um componente essencial para a implantação da nuvem.

---
---

##### Exemplo de uso de uma função do IAM:
![[Pasted image 20240910154130.png]]
No diagrama, um desenvolvedor executa um aplicativo em uma instância do EC2 que requer acesso ao bucket do S3 chamado photos. Um administrador cria a função do IAM e anexa a função à instância do EC2. A função inclui uma política de permissões que concede acesso somente leitura ao bucket do S3 especificado. Ele também inclui uma política de confiança que permite que a instância do EC2 assuma a função e recupere as credenciais temporárias. Quando o aplicativo é executado na instância, ele pode usar as credenciais temporárias da função para acessar o bucket photos. O administrador não precisa conceder ao desenvolvedor do aplicativo permissão para acessar o bucket photos, e o desenvolvedor nunca precisa compartilhar ou gerenciar credenciais.

Para saber mais detalhes sobre este exemplo, consulte [Uso de uma função do IAM para conceder permissões a aplicativos em execução em instâncias do](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html) [Amazon](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html) [EC2](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html). 

---
---

#ResumoSeção2Mod3

- As políticas do IAM são criadas com JavaScript Object Notation (JSON) e definem permissões.
	- As políticas do IAM podem ser anexadas a qualquer entidade do IAM.
	- As entidades são usuários do IAM, grupos do IAMe funções do IAM.
- Um usuário do IAM fornece uma maneirapara uma pessoa, um aplicativo ou um serviçose autenticar na AWS.
- Um grupo do IAM é uma maneira simples de anexar as mesmas políticas a vários usuários.
- Uma função do IAM pode ter políticasde permissões anexadas a ela e ser usadapara delegar acesso temporário a usuáriosou aplicativos.
