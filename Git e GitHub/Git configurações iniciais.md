Para configurarmos o git
De início, utilizamos o `git --global user.name` e colocamos nosso nome dentro de aspas
após isso,utilizamos o `git --global user.email` para adicionarmos nosso email.
`cd ..` volta um diretório, e `cd caminho_desejado

e o `git --global --list` para verificarmos as informações atuais, como o nome da branch, nome e email do usuário.

Para entrar em seu repositório do github pleo git, utilizamos o #gitclone `git clone urlGitHub ` assim entramos no nosso repositório 

`$ git config --global --list
`user.name=Matheus Avolio
`user.email=avoliomatheus.sed@Gmail.com

`mavol@avolio MINGW64 ~
`$ git clone https://github.com/matheusavolio/teste-git.git
`Cloning into 'teste-git'...
`remote: Enumerating objects: 3, done.
`remote: Counting objects: 100% (3/3), done.
`remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
`Receiving objects: 100% (3/3), done.

`mavol@avolio MINGW64 ~
`$ cd teste-git

`mavol@avolio MINGW64 ~/teste-git (main)
`$ git status
`On branch main
`Your branch is up to date with 'origin/main'.

`nothing to commit, working tree clean

# Materiais de apoio: 
![[Versionamento de Código com Git e GitHub (1).pdf]]

https://github.com/elidianaandrade/dio-curso-git-github?tab=readme-ov-file

`$ mkdir repo-local` cria um repositório local dentro da pasta que você está trabalhando

`git ini ` inicia o repositporio 
podemos utilizar um arquivo `.gitkeep` para utilizar em pastas vazias para o git reconhecer na árvore de trabalho.

`git log` mostra o histórico de commits

`git reset --soft números do commit` ele pega os arquivos que estavam nos commits posteriores e adicionam ele a área de preparação

`mkdir` - cria pastas no repositório atual
`touch` - cria arquivos no repositório atual


`main -> main (fetch first) error: failed to push some refs to 'github.com:matheusavolio/Estudos-Python.git' hint: Updates were rejected because the remote contains work that you do not hint: have locally. This is usually caused by another repository pushing to hint: the same ref. If you want to integrate the remote changes, use hint: 'git pull' before pushing again. hint: See the 'Note about fast-forwards' in 'git push --help' for details.

erro comum acima, para concertar




``mavol@avolio MINGW64 ~
`$ cd ..

mavol@avolio MINGW64 /c/Users
$ cd .

mavol@avolio MINGW64 /c/Users
$ cd ..

mavol@avolio MINGW64 /c
$ cd ..

mavol@avolio MINGW64 /
$ d
bash: d: command not found

mavol@avolio MINGW64 /
$ cd d

mavol@avolio MINGW64 /d
$ cd 'exercicios python'

mavol@avolio MINGW64 /d/exercicios python
$ git init
Initialized empty Git repository in D:/Exercicios python/.git/

mavol@avolio MINGW64 /d/exercicios python (master)
$ ls
'E.D python brasil'/  'Mundo 1'/  'Mundo 3'/   Treinos/
'E.S python brasil'/  'Mundo 2'/   README.md   netacd.cisco/

mavol@avolio MINGW64 /d/exercicios python (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Treinos/teste_git.py

no changes added to commit (use "git add" and/or "git commit -a")

mavol@avolio MINGW64 /d/exercicios python (master)
$ cd treinos

mavol@avolio MINGW64 /d/exercicios python/treinos (master)
$ git add teste_git.py

mavol@avolio MINGW64 /d/exercicios python/treinos (master)
$ git commit "Alterando arquivo e subindo ele, 3.0"
error: pathspec 'Alterando arquivo e subindo ele, 3.0' did not match any file(s) known to git

mavol@avolio MINGW64 /d/exercicios python/treinos (master)
$ git commit -m "Alterando arquivo e subindo ele, 3.0"
[master 9e4cc92] Alterando arquivo e subindo ele, 3.0
 1 file changed, 1 insertion(+)

mavol@avolio MINGW64 /d/exercicios python/treinos (master)
$ git remote add origin https://github.com/matheusavolio/Estudos-Python.git

mavol@avolio MINGW64 /d/exercicios python/treinos (master)
$ git push origin
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


mavol@avolio MINGW64 /d/exercicios python/treinos (master)
$ git push -u origin
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


mavol@avolio MINGW64 /d/exercicios python/treinos (master)
$ git branch -m main

mavol@avolio MINGW64 /d/exercicios python/treinos (main)
$ git push origin main
git: 'credential-manager-core' is not a git command. See 'git --help'.
To https://github.com/matheusavolio/Estudos-Python.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/matheusavolio/Estudos-Python.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

mavol@avolio MINGW64 /d/exercicios python/treinos (main)
$ git fetch
git pgit: 'credential-manager-core' is not a git command. See 'git --help'.
ullremote: Enumerating objects: 175, done.
remote: Counting objects: 100% (175/175), done.
remote: Compressing objects: 100% (165/165), done.
remote: Total 175 (delta 6), reused 171 (delta 5), pack-reused 0 (from 0)
Receiving objects: 100% (175/175), 46.27 KiB | 1008.00 KiB/s, done.
Resolving deltas: 100% (6/6), done.
From https://github.com/matheusavolio/Estudos-Python
 * [new branch]      main       -> origin/main
o
mavol@avolio MINGW64 /d/exercicios python/treinos (main)
$ git pull origin
git: 'credential-manager-core' is not a git command. See 'git --help'.
You asked to pull from the remote 'origin', but did not specify
a branch. Because this is not the default configured remote
for your current branch, you must specify a branch on the command line.

mavol@avolio MINGW64 /d/exercicios python/treinos (main)
$ git push origin main
git: 'credential-manager-core' is not a git command. See 'git --help'.
To https://github.com/matheusavolio/Estudos-Python.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/matheusavolio/Estudos-Python.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. If you want to integrate the remote changes,
hint: use 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

mavol@avolio MINGW64 /d/exercicios python/treinos (main)
$ git push -u origin main
git: 'credential-manager-core' is not a git command. See 'git --help'.
To https://github.com/matheusavolio/Estudos-Python.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/matheusavolio/Estudos-Python.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. If you want to integrate the remote changes,
hint: use 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

mavol@avolio MINGW64 /d/exercicios python/treinos (main)
$ git push --force origin main
git: 'credential-manager-core' is not a git command. See 'git --help'.
Enumerating objects: 168, done.
Counting objects: 100% (168/168), done.
Delta compression using up to 8 threads
Compressing objects: 100% (164/164), done.
Writing objects: 100% (168/168), 44.94 KiB | 22.47 MiB/s, done.
Total 168 (delta 3), reused 159 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/matheusavolio/Estudos-Python.git
 + 71adeab...9e4cc92 main -> main (forced update)

mavol@avolio MINGW64 /d/exercicios python/treinos (main)
$ git status
On branch main
nothing to commit, working tree clean

mavol@avolio MINGW64 /d/exercicios python/treinos (main)
$ cd ..

mavol@avolio MINGW64 /d/exercicios python (main)
$ git status
On branch main
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    netacd.cisco/3.1.1.10.py
        deleted:    netacd.cisco/3.1.1.11.py
        deleted:    netacd.cisco/3.1.1.12.py

no changes added to commit (use "git add" and/or "git commit -a")

mavol@avolio MINGW64 /d/exercicios python (main)
$ git add netacd.cisco

mavol@avolio MINGW64 /d/exercicios python (main)
$ git commit -m "netacd.cisco removidos"
[main 4fffdfc] netacd.cisco removidos
 3 files changed, 69 deletions(-)
 delete mode 100644 netacd.cisco/3.1.1.10.py
 delete mode 100644 netacd.cisco/3.1.1.11.py
 delete mode 100644 netacd.cisco/3.1.1.12.py

mavol@avolio MINGW64 /d/exercicios python (main)
$ git push origin main
git: 'credential-manager-core' is not a git command. See 'git --help'.
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 235 bytes | 235.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/matheusavolio/Estudos-Python.git
   9e4cc92..4fffdfc  main -> main
``
``

https://github.com/matheusavolio/dio-lab-open-source