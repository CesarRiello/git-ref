# git-ref
Referência de comandos de git

CONFIG
--------------------

 **git config**<opção> <parâmetro>

- opção: **--system** (todo o sistema) 
edita arquivo: /etc/gitconfig

- opção: **--global** (apenas o usuário)
edita o arquivo: ~/.gitconfig

- **local** editando arquivo:
**<repositorio>/config**
– válido para aquele repositório apenas

- opção: **--list** mostra configurações atuais do ambiente git 

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

opção: **-v** – Mostra detalhes dos remotos

**git remote add**<nome> <url>

- adiciona um repositório
remoto ao projeto atual

VERSIONAMENTO
-----------------------------------------------

**git status**

- verifica o estado do seu
working dir. (untracked, unmodified, modified, staged)

opção: **-s
**ou **–short**
– versão compacta do status

**git add **<arquivo>

- adiciona arquivos para o
stage / monitoramento

**git rm **<arquivo>
<opções>

- remove arquivos do
repositório e do seu working dir.

**git commit**
<opções>

- grava arquivos do stage para
o repositório

**git log **<opções>

- mostra histórico de commits

opção: **--stat**– mostra
pequeno resumo de alterações nos arquivos daquele commit

opção: **--pretty=**<parâmetro>
- diversas opções de formatação do log

- parâmetro:**oneline**
– mostra uma lista abreviada de commit + mensagem de commit

- parâmetro:**format:**“<formato>”
- Formata saída do log conforme preferência do usuário.

Exemplo para teste: 

git log --pretty=format:“%h - %an, %ar : %s”

**git tag**
<nome da tag>

- marca versão do software
(release point), no commit atual

opção: **-a**
– cria uma tag anotada (mais informações são adicionadas)

**git push**
<nome remoto> <branch>

- publica branch especificado no repositório remoto

**git fetch**
<nome remoto>

- baixa para seu repositório local o trabalho realizado no remoto.
(sem merge)

**git pull**
<nome remoto>

- baixa e mescla (merge) o trabalho do realizado no remoto com seu
repositório local

DESFAZENDO
-----------------------------------------------
COISAS
-----------------------------------------------

**git commit --amend**

- edita e sobrescreve o último commit

**git reset HEAD **<arquivo>

- retira arquivo do stage

**git checkout **--<arquivo>

- reverte arquivo para sua versão no último commit

BRANCHING
-----------------------------------------------
 **git branch **<nome novo branch>

- cria um novo branch. Sem parâmetros mostra os branches atuais

**git checkout **<branch>

- muda seu working dir para o branch especificado. Com a opção **-b**,
cria um novo branch e move o working dir para ele

**git merge **<branch>

- mescla o branch do comando no seu branch atual


LOG
-----------------------------------------------
OPÇÕES
ÚTEIS PARA: 

**git log** --prety=format:

|---:|----:|----:|
|%H | Commit | hash  |
|%h | Commit | hash Abreviado |
|%T | Hash | da árvore |
|%t | Hash | da árvore abreviado |
|%P | Hashes | pais |
|%p | Hashes | pais abreviados |
|%an | Nome | do Autor |
|%ae | Email | do Autor |
|%ad | Data | do autor  |
|%ar | Data | do autor, relativa |
|%cn | Nome | do Comitter |
|%ce | Email | do committer |
|%cd | Data | do committer |
|%cr | Data | do committer, relativa |
|%s | Assunto | (mensagem do commit) |
