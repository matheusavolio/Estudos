
# #Git

### 1. **Introdução ao Git**

- **O que é Git?**
    - Sistema de controle de versão distribuído
    - Gerencia e rastreia alterações em arquivos
- **Principais Conceitos**
    - Repositório
    - Commit
    - Branch
    - Merge
    - Pull e Push

### Mapa Mental: Fluxo de Trabalho do Git

**1. Configuração Inicial**

- **Instalar Git**:
    - Baixe e instale o Git no [site oficial](https://git-scm.com/).
- **Configurar Identidade**:
    
    bash
    
    Copiar código
    
    `git config --global user.name "Seu Nome" 
    `git config --global user.email "seuemail@example.com"`
    
    - **Exemplo**: `git config --global user.name "Matheus Avolio"`

**2. Criar um Repositório Local**

- **Inicializar o Repositório**:
    

    
    `git init`
    
    - **Exemplo**: Inicia um repositório em um diretório chamado `meu-projeto`.
- **Verificar o Status**:
    
    
    `git status`
    
    - **Exemplo**: Mostra arquivos não rastreados e mudanças pendentes.

**3. Fazer Modificações**

- **Adicionar Arquivos**:
    
    
    `git add <arquivo>       # Adicionar arquivos específicos 
    `git add .               # Adicionar todos os arquivos modificados`
    
    - **Exemplo**: Adiciona `index.html` e `style.css` ao índice.
- **Verificar o Status dos Arquivos**:
    
    
    `git status`
    
    - **Exemplo**: Mostra que `index.html` está pronto para commit.

**4. Commit das Alterações**

- **Fazer Commit**:
    
    
    `git commit -m "Mensagem do commit"`
    
    - **Exemplo**: `git commit -m "Adiciona página inicial com estrutura básica"`

**5. Conectar ao Repositório Remoto**

- **Adicionar o Repositório Remoto**:
    
    `git remote add origin https://github.com/usuario/repositorio.git`
    
    - **Exemplo**: `git remote add origin https://github.com/matheusavolio/meu-repositorio.git`
- **Verificar Remotos Configurados**:
    
    
    `git remote -v`
    
    - **Exemplo**: Mostra `origin https://github.com/matheusavolio/meu-repositorio.git (fetch)` e `(push)`

**6. Enviar Alterações para o GitHub**

- **Enviar as Alterações (Push)**:
    
    
    `git push -u origin main`
    
    - **Exemplo**: Envia suas alterações na branch `main` para o repositório remoto no GitHub.

**7. Sincronizar com o Repositório Remoto**

- **Buscar Atualizações**:
    
    
    `git fetch`
    
    - **Exemplo**: Baixa alterações do repositório remoto sem integrá-las.
- **Integrar Alterações**:
    
    bash
    
    Copiar código
    
    `git pull origin main`
    
    - **Exemplo**: Baixa e mescla alterações da branch `main` do repositório remoto.

**8. Manutenção do Repositório**

- **Verificar Histórico de Commits**:
    
    
    `git log`
    
    - **Exemplo**: Exibe o histórico de commits, mostrando IDs, mensagens e autores.
- **Criar e Alternar Branches**:
    
    
    `git branch <nome-da-branch>   # Criar uma nova branch 
    `git checkout <nome-da-branch> # Alternar para a branch`
    
    - **Exemplo**: `git branch feature-login` e `git checkout feature-login`
- **Mesclar Branches**:
    
    
    `git checkout main            # Voltar para a branch principal 
    `git merge <nome-da-branch>   # Mesclar outra branch na branch atual`
    
    - **Exemplo**: `git checkout main` e `git merge feature-login`

**9. Trabalhar com Branches**

- **Criar uma Nova Branch**:
    
    bash
    
    Copiar código
    
    `git checkout -b <nome-da-branch>`
    
    - **Exemplo**: `git checkout -b feature-login`
- **Excluir uma Branch**:
    
    bash
    
    Copiar código
    
    `git branch -d <nome-da-branch>`
    
    - **Exemplo**: `git branch -d feature-login`

### Resumo do Fluxo de Trabalho

1. **Configuração Inicial**: Instalar e configurar Git.
2. **Criar um Repositório Local**: Inicializar e verificar o repositório.
3. **Fazer Modificações**: Adicionar arquivos e verificar status.
4. **Commit das Alterações**: Fazer commit das alterações.
5. **Conectar ao Repositório Remoto**: Adicionar e verificar o repositório remoto.
6. **Enviar Alterações para o GitHub**: Enviar alterações para o repositório remoto.
7. **Sincronizar com o Repositório Remoto**: Buscar e integrar atualizações.
8. **Manutenção do Repositório**: Verificar histórico, criar e alternar branches.
9. **Trabalhar com Branches**: Criar, alternar e excluir branches.

---

### **Mapa Mental Detalhado: Comandos de Terminal do Git**


**1. **Configuração**

- **`git config`**: Configura opções do Git.
    - **`git config --global user.name "Seu Nome"`**: Configura o nome do usuário.
        
        
        `git config --global user.name "Matheus Avolio"`
        
    - **`git config --global user.email "email@example.com"`**: Configura o email do usuário.
        
        
        `git config --global user.email "avoliomatheus.sed@gmail.com"`
        
    - **`git config --global core.editor "editor"`**: Configura o editor de texto.
        
        
        `git config --global core.editor "vim"`
        

---

**2. **Criação e Inicialização**

- **`git init`**: Inicializa um novo repositório Git.
    
    
    `git init`
    
- **`git clone <url>`**: Clona um repositório remoto.
    
    
    `git clone https://github.com/usuario/repositorio.git`
    

---

**3. **Status e Histórico**

- **`git status`**: Mostra o status das alterações.
    
    
    `git status`
    
- **`git log`**: Exibe o histórico de commits.
    
    
    `git log`
    
    - **`git log --oneline`**: Exibe o histórico em uma linha por commit.
        
        
        `git log --oneline`
        

---

**4. **Modificação e Adição**

- **`git add <arquivo>`**: Adiciona arquivos à área de preparação.
    - **`git add <arquivo>`**: Adiciona um arquivo específico.
        
        `git add treino.py`
        
    - **`git add .`**: Adiciona todos os arquivos modificados.
        
        
        `git add .`
        
- **`git rm <arquivo>`**: Remove arquivos do repositório e da área de preparação.
    
    
    `git rm arquivo.txt`
    

---

**5. **Commit**

- **`git commit -m "mensagem"`**: Faz um commit com uma mensagem.
    
    
    `git commit -m "Corrige bug na função de cálculo"`
    
- **`git commit --amend`**: Modifica o último commit.
    
    
    `git commit --amend`
    

---

**6. **Branches**

- **`git branch`**: Lista, cria ou exclui branches.
    - **`git branch <nome>`**: Cria uma nova branch.
        
        `git branch feature-xyz`
        
    - **`git branch -d <nome>`**: Exclui uma branch.
        
        
        `git branch -d feature-xyz`
        
- **`git checkout <nome>`**: Muda para uma branch existente.
    
    
    `git checkout main`
    
- **`git checkout -b <nome>`**: Cria e muda para uma nova branch.
    
    
    `git checkout -b feature-xyz`
    
- **`git merge <branch>`**: Mescla a branch especificada com a branch atual.
    
    
    `git merge feature-xyz`
    
- **`git rebase <branch>`**: Reaplica commits em uma nova base.
    
    
    `git rebase main`
    

---

**7. **Sincronização com o Repositório Remoto**

- **`git remote`**: Gerencia repositórios remotos.
    - **`git remote add <nome> <url>`**: Adiciona um novo repositório remoto.
        
        
        `git remote add origin https://github.com/usuario/repositorio.git`
        
    - **`git remote remove <nome>`**: Remove um repositório remoto.
        
        
        `git remote remove origin`
        
- **`git fetch`**: Obtém alterações do repositório remoto.
    
    
    `git fetch`
    
- **`git pull`**: Obtém e mescla alterações do repositório remoto.
    
    
    `git pull origin main`
    
- **`git push`**: Envia alterações para o repositório remoto.
    - **`git push -u <nome> <branch>`**: Define a branch upstream para o repositório remoto.
        
        
        `git push -u origin main`
        

---

**8. **Reverter e Resetar**

- **`git reset`**: Reverte o HEAD e ajusta a área de preparação.
    - **`git reset --soft <commit>`**: Mantém alterações na área de preparação.
        
        
        `git reset --soft HEAD~1`
        
    - **`git reset --mixed <commit>`**: Limpa a área de preparação.
        
        
        `git reset --mixed HEAD~1`
        
    - **`git reset --hard <commit>`**: Remove alterações na área de preparação e diretório de trabalho.
        
        
        `git reset --hard HEAD~1`
        
- **`git revert <commit>`**: Cria um novo commit que reverte alterações do commit especificado.
    
    
    `git revert abc123`
    

---

**9. **Comparação e Diferenças**

- **`git diff`**: Mostra as diferenças entre commits, branches ou arquivos.
    - **`git diff`**: Mostra diferenças não comitadas.
        
        
        `git diff`
        
    - **`git diff --staged`**: Mostra as diferenças entre a área de preparação e o último commit.
        
        
        `git diff --staged`
        
    - **`git diff <branch1> <branch2>`**: Compara duas branches.
        
        
        `git diff main feature-xyz`
        

---

**10. **Stash**

- **`git stash`**: Salva alterações não comitadas.
    
    
    `git stash`
    
    - **`git stash pop`**: Aplica e remove o stash.
        
        
        `git stash pop`
        
    - **`git stash list`**: Lista stashes salvos.
        
        
        `git stash list`
        
    - **`git stash apply`**: Aplica o stash sem removê-lo.
        
        
        `git stash apply`
        

---

**11. **Tagging**

- **`git tag`**: Cria, lista ou exclui tags.
    - **`git tag <tag>`**: Cria uma nova tag.
        
        
        `git tag v1.0`
        
    - **`git tag -d <tag>`**: Exclui uma tag.
        
        
        `git tag -d v1.0`
        

---

**12. **Rebase**

- **`git rebase <branch>`**: Reaplica commits em uma nova base.
    
    
    `git rebase main`
    
    - **`git rebase -i <commit>`**: Inicia um rebase interativo.
        
        
        `git rebase -i HEAD~3`
        

---

**13. **Outros Comandos**

- **`git show <commit>`**: Mostra detalhes de um commit específico.
    
    
    `git show abc123`
    
- **`git clean`**: Remove arquivos não rastreados do diretório de trabalho.
    - **`git clean -f`**: Força a remoção de arquivos não rastreados.
        
        
        `git clean -f`
        

---

### **Resumo**

- **Configuração**: `git config`
- **Criação e Inicialização**: `git init`, `git clone`
- **Status e Histórico**: `git status`, `git log`
- **Modificação e Adição**: `git add`, `git rm`
- **Commit**: `git commit`, `git commit --amend`
- **Branches**: `git branch`, `git checkout`, `git merge`, `git rebase`
- **Sincronização com o Repositório Remoto**: `git remote`, `git fetch`, `git pull`, `git push`
- **Reverter e Resetar**: `git reset`, `git revert`
- **Comparação e Diferenças**: `git diff`
- **Stash**: `git stash`
- **Tagging**: `git tag`
- **Rebase**: `git rebase`
- **Outros Comandos**: `git show`, `git clean`


### Mapa Mental: Branches no Git

#### 1. **O que é uma Branch?**

- **Definição**: Uma branch é uma linha separada de desenvolvimento dentro de um repositório Git, permitindo que múltiplos desenvolvedores trabalhem simultaneamente sem interferir uns nos outros.
- **Utilidade**: Facilita o trabalho em novas funcionalidades, correção de bugs e experimentações sem impactar a branch principal (geralmente `main` ou `master`).

#### 2. **Tipos de Branches**

- **Branch Principal**:
    - Geralmente nomeada como `main` ou `master`.
    - Contém o código mais estável e pronto para produção.
- **Branch de Funcionalidade**:
    - Criada a partir da branch principal para desenvolver uma nova funcionalidade ou recurso.
    - Exemplo: `git checkout -b nova-funcionalidade`.
- **Branch de Correção de Bug**:
    - Criada para corrigir bugs específicos.
    - Exemplo: `git checkout -b correcao-bug-123`.
- **Branch de Hotfix**:
    - Utilizada para corrigir problemas críticos na branch principal e lançar rapidamente.
    - Exemplo: `git checkout -b hotfix-critico`.

#### 3. **Operações com Branches**

- **Criar uma Branch**:
    - Comando: `git branch nome-da-branch`
    - Exemplo: `git branch feature-login`
- **Mudar para uma Branch**:
    - Comando: `git checkout nome-da-branch`
    - Exemplo: `git checkout feature-login`
- **Criar e Mudar para uma Nova Branch**:
    - Comando: `git checkout -b nome-da-branch`
    - Exemplo: `git checkout -b correcao-bug-404`
- **Listar Branches**:
    - Comando: `git branch`
    - Exibe todas as branches locais e destaca a atual.
- **Mesclar uma Branch**:
    - Comando: `git merge nome-da-branch`
    - Exemplo: Mesclando `feature-login` na `main`: `git checkout main` seguido de `git merge feature-login`.
- **Excluir uma Branch**:
    - Comando: `git branch -d nome-da-branch`
    - Exemplo: `git branch -d feature-antiga`

#### 4. **Fluxo de Trabalho Comum com Branches**

- **Desenvolvimento de Nova Funcionalidade**:
    1. Criar uma branch de funcionalidade a partir da branch principal.
    2. Desenvolver a funcionalidade na nova branch.
    3. Fazer commits das alterações.
    4. Mesclar a branch de funcionalidade na branch principal após a conclusão e testes.
    5. Excluir a branch de funcionalidade após a mesclagem.
- **Correção de Bugs**:
    1. Criar uma branch de correção de bug a partir da branch principal.
    2. Corrigir o bug e fazer commits.
    3. Mesclar a branch de correção de bug na branch principal.
    4. Excluir a branch de correção de bug.

#### 5. **Exemplos Práticos**

- **Exemplo 1**: Criando uma branch para adicionar um novo recurso de autenticação:
    
    
    `git checkout -b recurso-autenticacao`
    
    Desenvolver o recurso e depois mesclar com a principal:
    
    bash
    
    Copiar código
    
    `git checkout main 
    `git merge recurso-autenticacao`
    
- **Exemplo 2**: Criando uma branch para corrigir um bug crítico:
    
    bash
    
    Copiar código
    
    `git checkout -b bug-critico-correção`
    
    Após corrigir, mesclar de volta na principal:
    
    
    `git checkout main 
    `git merge bug-critico-correção`
    

Este mapa mental oferece uma visão detalhada sobre o uso de branches no Git, permitindo que os desenvolvedores trabalhem de forma organizada e colaborativa.



![[Versionamento de Código com Git e GitHub (1).pdf]]


![[git-guia-basico.pdf]]

![[Contribuindo em um Projeto Open Source no GitHub.pdf]]

### 1) Faça um **Fork** deste Repositório

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#1-fa%C3%A7a-um-fork-deste-reposit%C3%B3rio)

Acesse a página principal do repositório e clique no botão "Fork" no canto superior direito da página.

Note

Um "fork" no GitHub é uma cópia de um repositório que pode ser criada por qualquer usuário.  
Para mais detalhes, reveja a aula ou acesse a documentação do GitHub: [Criar fork de um repositório](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo).

### 2) Clone localmente

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#2-clone-localmente)

Abra o seu Git Bash e digite o comando `git clone` seguido da URL do seu fork para clonar o seu repositório localmente. Por exemplo:

```shell
git clone https://github.com/SEU_USERNAME/dio-lab-open-source.git
```

Pressione enter, e uma cópia do seu fork no GitHub será criada localmente.

### 3) Crie uma nova **branch**

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#3-crie-uma-nova-branch)

Utilize o comando `git checkout -b` para criar e alternar para a nova branch e nomeie-a como `feat/community/SEU_USERNAME`

> Exemplo: `git checkout -b feat/community/falvojr`

### 4) Crie o seu Profile README

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#4-crie-o-seu-profile-readme)

Dentro da pasta [`community`](https://github.com/digitalinnovationone/dio-lab-open-source/tree/main/community), crie um arquivo em Markdown (extensão `.md`) e nomeie com o mesmo nome do seu usuário no GitHub:

> Exemplo: `community/falvojr.md`

#### 4.1) Desenvolva o seu Profile README

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#41-desenvolva-o-seu-profile-readme)

Para isso, você pode se inspirar nos exemplos no diretório [`community`](https://github.com/digitalinnovationone/dio-lab-open-source/tree/main/community) e adicionar alguns dos utilitários presentes na pasta [`utils`](https://github.com/digitalinnovationone/dio-lab-open-source/tree/main/utils)

### 5) Adicione suas alterações à "staging area"

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#5-adicione-suas-altera%C3%A7%C3%B5es-%C3%A0-staging-area)

Utilize o comando `git add community/SEU_USERNAME.md` para adicionar sua alteração (nesse caso o arquivo markdown criado) à "staging area" no Git.

### 6) Crie um Commit

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#6-crie-um-commit)

Crie um commit e adicione a mensagem indicando a adição do seu perfil:

```shell
git commit -m"feat: add SEU_USERNAME profile"
```

Important

Verifique a [`Convenção de Commits`](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#conven%C3%A7%C3%A3o-de-commits) para escrever a mensagem do seu commit de forma clara e padronizada.

### 7) Envie as Alterações para o seu Repositório Remoto

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#7-envie-as-altera%C3%A7%C3%B5es-para-o-seu-reposit%C3%B3rio-remoto)

Envie as alterações realizadas no seu repositório local para a branch `feat/community/SEU_USERNAME` no seu repositório remoto com o comando:

```shell
git push origin feat/community/SEU_USERNAME
```

Warning

Caso você tenha criado seu arquivo diretamente no repositório remoto no GitHub, esse processo não será necessário.

### 8) Crie um **Pull Request**.

[](https://github.com/digitalinnovationone/dio-lab-open-source/blob/main/CONTRIBUTING.md#8-crie-um-pull-request)

Atente-se para a seguir as orientações para a contribuição, principalmente:

- Seu PR deve modificar apenas o arquivo community/SEU_USERNAME.md (dê uma olhadinha na aba "Files changed");
- O nome desse arquivo deve ser exatamente igual ao nome de usuário no GitHub (nossa validação é case-sensitive).

Note

Caso não saiba como criar uma solicitação de pull, reveja o lab ou acesse a documentação do GitHub: [Como criar uma solicitação de pull](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

Após criar o seu Pull Request, nossa automação irá validar a sua submissão. Caso esteja tudo certo, será retornada uma mensagem indicado que seu PR foi aprovado. Do contrário, leia atentamente as orientações e verifique os arquivos modificados para saber se atende as instruções para contribuição.

------------------------------------------------------------------------
------------------------------------------------------------------------

# #GitHub 
### 1. **Introdução ao GitHub**

- **O que é GitHub?**
    - Plataforma de hospedagem para repositórios Git
    - Funcionalidades para colaboração e controle de versões
- **Principais Conceitos**
    - Repositório
    - Pull Request
    - Issues
    - Fork
    - Stars e Watchers


### Mapa Mental: Fluxo de Trabalho no GitHub

**1. Criar uma Conta no GitHub**

- **Registrar-se**: Acesse [GitHub](https://github.com/) e clique em "Sign up".
- **Exemplo**: Crie uma conta com o nome de usuário `matheusavolio`.

**2. Criar um Novo Repositório no GitHub**

- **Iniciar Novo Repositório**:
    - Navegue até a página inicial do GitHub.
    - Clique em **New** no menu de repositórios.
- **Configurar Repositório**:
    - **Nome do Repositório**: `teste-git`
    - **Descrição**: "Repositório de teste para aprendizado de Git e GitHub"
    - **Visibilidade**: Público ou Privado
    - **Inicializar com um README**: Se desejar iniciar com um README.
    - **Adicionar um .gitignore**: Selecione a linguagem (por exemplo, Python).
    - **Escolher uma Licença**: (Opcional) Adicione uma licença como MIT.
- **Criar Repositório**: Clique em **Create repository**.

**3. Clonar o Repositório para o Seu Computador**

- **Obter URL do Repositório**:
    - Acesse a página do repositório e copie a URL.
- **Clonar Repositório**:
    
    bash
    
    Copiar código
    
    `git clone https://github.com/matheusavolio/teste-git.git`
    
- **Exemplo**: Clonando o repositório `teste-git` para sua máquina local.

**4. Trabalhar com o Repositório Localmente**

- **Adicionar e Modificar Arquivos**:
    - Adicione um novo arquivo ou modifique arquivos existentes.
    - Exemplo: Crie um arquivo `index.html` com o conteúdo básico.
- **Commit e Push**:
    
    bash
    
    Copiar código
    
    `git add index.html git commit -m "Adiciona arquivo index.html" git push origin main`
    
- **Exemplo**: Faça um commit com uma mensagem descritiva e envie as alterações para o GitHub.

**5. Gerenciar Repositórios no GitHub**

- **Configurações do Repositório**:
    - **Configurações Gerais**: Nome, descrição, visibilidade.
    - **Gerenciar Colaboradores**: Adicione colaboradores como `joao` e `maria`.
    - **Configurar Webhooks**: Para integração com ferramentas externas.
    - **Configurar Branches**: Proteja a branch `main`.
- **Visualizar Estatísticas**:
    - **Commits**: Navegue para **Insights** para ver o histórico de commits.
    - **Branches**: Verifique as branches no menu **Branches**.
    - **Contributors**: Veja contribuições na aba **Contributors**.

**6. Trabalhar com Branches no GitHub**

- **Criar Branches**:
    - Navegue até a aba **Branches**.
    - Clique em **New branch** e nomeie como `feature/login`.
- **Gerenciar Branches**:
    - **Alternar entre Branches**: Selecione `feature/login` na lista de branches.
    - **Excluir Branches**: Clique em **Delete branch** ao lado de uma branch obsoleta.

**7. Pull Requests (PRs)**

- **Criar um Pull Request**:
    - Navegue até a aba **Pull requests**.
    - Clique em **New pull request**.
    - Compare `feature/login` com `main`, adicione uma descrição e clique em **Create pull request**.
- **Revisar Pull Requests**:
    - **Comentários e Revisões**: Adicione comentários e sugestões no PR.
- **Mesclar Pull Requests**:
    - Clique em **Merge pull request** e confirme para integrar as alterações.

**8. Issues e Projetos**

- **Criar Issues**:
    - Navegue até a aba **Issues**.
    - Clique em **New issue** e forneça um título e descrição, como "Correção de bug no login".
- **Gerenciar Issues**:
    - **Atribuir**: Atribua a issue para um colaborador específico.
    - **Rótulos e Milestones**: Adicione um rótulo "bug" e defina uma milestone.
- **Gerenciar Projetos**:
    - **Criar Projetos**: Use quadros Kanban, como "Desenvolvimento", "Revisão", "Concluído".

**9. Colaboração e Comunidade**

- **Fork Repositórios**:
    - Navegue até um repositório interessante e clique em **Fork** para criar uma cópia.
- **Star Repositórios**:
    - Clique em **Star** no repositório para marcar como favorito.
- **Seguir Outros Usuários**:
    - Navegue até o perfil de um usuário e clique em **Follow** para acompanhar suas atividades.

### Resumo do Fluxo de Trabalho no GitHub

1. **Criar Conta**: Registrar-se no GitHub.
2. **Criar Repositório**: Configurar e criar um novo repositório.
3. **Clonar Repositório**: Baixar o repositório para o computador.
4. **Trabalhar Localmente**: Modificar arquivos e enviar alterações.
5. **Gerenciar Repositório**: Configurações, colaboradores e estatísticas.
6. **Trabalhar com Branches**: Criar, alternar e gerenciar branches.
7. **Pull Requests**: Criar, revisar e mesclar pull requests.
8. **Issues e Projetos**: Criar e gerenciar issues e projetos.
9. **Colaboração e Comunidade**: Fork, star e seguir usuários.
