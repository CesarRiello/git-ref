# git-ref
Referência de comandos de git

CONFIG
--------------------
 **git config**<opção> <parâmetro>

- opção: **--system** (todo o sistema) 
edita arquivo: /etc/gitconfig

- opção: **--global** (apenas o usuário)
edita o arquivo: ~/.gitconfig

- opção: **--list** mostra configurações atuais do ambiente git 

**config local** editando arquivo:
**<repositorio>/config**

REPOSITÓRIOS
-----------------------------------------------
 **git init **

- inicializa repositório no modo working dir (.git dir)

**git init --bare**

- inicializa repositório no modo de armazenamento (compartilhável)

**git clone **<origem> <destino>
- clona repositório e seus atributos (local ou remoto)

**git remote **<opções>
- verifica e configura repositórios remotos (ou no mesmo filesystem)
 -opção: **-v** – Mostra detalhes dos remotos

**git remote add**<nome> <url>
- adiciona um repositório remoto ao projeto atual

VERSIONAMENTO
-----------------------------------------------

**git status**
verifica o estado do seu working dir. (untracked, unmodified, modified, staged)

**git status -s (ou –short)**
versão compacta do status

**git add **<arquivo>
adiciona arquivos para o stage / monitoramento

**git rm **<arquivo> <opções>
remove arquivos do repositório e do seu working dir.

**git commit** <opções>
grava arquivos do stage para o repositório

**git push** <nome remoto> <branch>
publica branch especificado no repositório remoto

**git fetch** <nome remoto>
baixa para seu repositório local o trabalho realizado no remoto.

**git pull** <nome remoto>
baixa e mescla (merge) o trabalho do realizado no remoto com seu repositório local

DESFAZENDO COISAS
-----------------------------------------------

**git commit --amend**
edita e sobrescreve o último commit

**git reset --soft** <commit>
desfaz o commit mantem as mudanças

**git reset --hard** <commit>
desfaz as alterações e commits

**git checkout **--<arquivo>
reverte arquivo para sua versão no último commit

**git checkout <branch>**--<arquivo>
reverte arquivo para sua versão da branch especificada

BRANCH E TAG
-----------------------------------------------
 **git branch **
 lista os branchs locais

**git branch -a**
 lista os branchs remotos

 **git branch **<nome>
 cria um novo branch.

**git checkout -b** <branch>
cria um novo branch e da checkout nele

**git checkout -b** <localBranchName> origin/<remoteBranchName>
cria um novo branch apartir do remoto

**git branch --delete **<branch>
**git branch -d **<branch>
apaga o branch local.

**git branch -D **<branch>
força o delete para branchs não mergeadas

**git push origin :**<branchName>
**git push origin --delete **<branchName>
 apaga o branch remoto.

**git tag** <nome>
marca versão do software (release point), no commit atual

**git tag -a** <nome>
cria uma tag anotada (mais informações são adicionadas)

git tag -d <nome>
deleta a tag

LOG
-----------------------------------------------

EXEMPLOS

**git log --all**
 todos os commits

**git log -n**
os últimos n commits

**git log -p**
mostra alterações

**git log --stat**
arquivos que foram alterados

**git log --oneline**
apenas uma linha

**git log --graph**
histórico em grafico ASCII

**git log --grep=**"<pattern>"
grep no log

**git log** <file>
log em um arquivo especifico

git log --decorate
mostra em que ponto esta o HEAD


**filtros**
**git log --author** "jose"
**git log --committer** "maria"
**git log --before** "2015-02-01"
**git log --after** 2.days.ago
**git log --after** "2015-03-01" **--before** "2015-06-01"
**git log --since**=2.weeks.ago **--until**=1.week.ago
git log --since=3.weeks --author=jlara --author=rgutierrez --all-match

OPÇÕES: 

**git log** --prety=format:

git log --pretty=format:"Commit Hash: %H, Author: %aN, Date: %aD"
git log --pretty=format:"%h%x09%an%x09%ad%x09%s"
git log --pretty=format:"%H %an %ad" --date=short
git log --format='%Cred%h%Creset %s %Cgreen(%cr) %C(blue)<%an>%Creset%C(yellow)%d%Creset' --no-merges
git log --pretty=format:"%C(yellow)%h%C(white) %ad %aN%x09%d%x09%s" --date=short
git log --graph --date=relative 
        --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%Creset'
git log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat
git log --pretty=format:"%C(yellow)%ad - %Creset%s%Cblue - [%cn]" --decorate --date=relative 
git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

| formato  | opção | o que |
| ------------- | ------------- | ------------- |
| %H  | Commit  | hash  |
| %h  | Commit  | hash Abreviado  |
| %T  |  Hash  |  da árvore  |
| %t  |  Hash  |  da árvore abreviado  |
| %P  |  Hashes  |  pais  |
| %p  |  Hashes  |  pais abreviados  |
| %an  |  Nome  |  do Autor  |
| %ae  |  Email  |  do Autor  |
| %ad  |  Data  |  do autor   |
| %ar  |  Data  |  do autor, relativa  |
| %cn  |  Nome  |  do Comitter  |
| %ce  |  Email  |  do committer  |
| %cd  |  Data  |  do committer  |
| %cr  |  Data  |  do committer, relativa  |
| %s  |  Assunto  |  (mensagem do commit)  |
