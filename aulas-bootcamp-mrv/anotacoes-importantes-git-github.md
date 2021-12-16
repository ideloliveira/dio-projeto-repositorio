# Introdução ao Git - versionamento de codigo distribuido

- Git - Ajuda a criar e a monitorar diferentes versões do código na máquina. Ele é um padrão de mercado, contanto já haviam antes do Git outros sistems de versionamento, tais como: Bitkeeper, CVS, Subversion.
- O Git e o Github commumente aparecem juntos em cursos, contanto são sistemas diferentes que se completam. O Git versiona o código e o GitHub é um repositorio online. Outros repositorios onlines são: Gitbucker e Gitlab.
- Beneficios de aprender essas tecnolpgias:
  - Controle de versão
  - Armazenamento em nuvens
  - Trabalho em Equipe
  - Melhora do código
  - Reconhecimento, pois o mesmo funciona tambem como uma rede social, ajudanto a espalhar os seus pra outros usuarios.

## Como o Git funciona por debaixo dos panos

- Sha1
- Objetos Fundamentais
- Sistema Distribuido
- Seguro

#### Sha1 - algoritimo de encriptação

(Security hash Algorithm)

- Sha1 é uma forma de identificar um arquivo. Foi desenvolvido pela NSA (Agencia de Segurança Nacional dos EUA).
- A encriptação gera conjuntos de caracteres identificados de 40 digitos.

#### Forma de lançar um encriptação SHA1 em um arquivo

Abra o GitBash (especie de terminal do Git) na pasta onde está o arquivo a ser encriptado (clicar no o botão direito dentro da pasta escolher o GitBash ou ir navegando no GitBash ate a pasta desejada) e em seguida digita o comando abaixo:

openssl sha1 (nome do arquivo)

#### Objetos internos do Git

- BLOBS
- TREES
- COMMITS

Os Blobs armazeam os arquivos encriptados encontraremso o tamanho do arquivo e conteúdo;

As trees referenciam os blobs e outras trees, tambem tem o tamanho e o conteudo

Os commits por sua vez referenciam as trees e os blobs e possui incriptação propria.

O git é um sistema distribuido, pois ele permite que varias pessoas possam alterar o mesmo arquivo e é seguro porque todas as modificações geradas nos encriptações com 40 caracteres são geradas, assim nunca a pessoa alterará o mesmo o arquivo original, pois as alterações sempre vão gerar copias do arquivo original com suas encriptações correspontendes.

### Chaves SSH e Token

SSH é uma forma de estabelecer um coneção segura entre maquinas.

#### Gerando chaves SSH

- Para gerar chaves SSH faça os procedimentos abaixo:

  - digite o comando: ssh-keygen -t ed25519 -C "digite o email" (utilize o mesmo email cadastrado do GitHub) [Enter] logo apois defina uma senha.
  - navegue até a pasta onde foi salvo a chave SSH publica que deve está no endereço: /c:/users/[seu usuario]/.ssh. logo apois abra o arquivo com  o comando, cat id_ed25519.pub. Copie todo o texto que for exibido e vá para a sua conta no GITHub.
  - No GitHub va para Setting - SSH and GPG e clique no botão New SSH Key.
  - Na tela que for aberta, dê um titulo para a sua chave SSH e logo abaixo colo todo o texto que fora copiado anteriormente.

  #### Iniciando o SSH Agente

digite o comando no GitBash: eval $(ssh-agent -s). indique o arquivo da shave privada com o comando - ssh-add id_ed25519

### Primeiros comndos com o GIT

- iniciando o GIT
- Iniciando o versionamento
- criando um commit

#### Iniciar o Git

- GIT INIT / GIT ADD / GIT COMMIT

##### Criando um repositório

Criar os diretorios e iniciar o git na pasta

 - git init(cria o repositorio)

##### Configura o Git

- git config --global e digite os parametros desejados exemplo: git config -- global user.name "digita o nome" e git config -- global user.email "digita o Email".
  - Usar o name e email utilizados na criação do GitHub.

##### Commitar o arquivo

- git add * (colocar todos os arquivos em stage)
- git commit -m "Digita um informação para o commit"

### Tracked ou Untraked

- Tracked - Arquivo que são rastreado pelo Git e são subdivididos em tres areas.
  - Unmodified - ainda nao foi modificado
  - Modified - é o unmodified que sofre uma alteração
  - Stage - são onde os arquivos estão se preparando para fazer parte de um outro tipo de agrupamento. o arquivo no staged estão se preprando pra entrar no commit.
- Untraked - Arquivos que o Git nao tem ciência



​										|Remote Repository

Área de Desenvolvimento					|

:-----------------------------------|:-------------------------:|---------------------------:

Work Directory                | Staging Area           | Local Repository   |

-----------------------------------|----------------------------|--------------------------|

**Git Status** Informa o estado do arquivo no momento

- verificando o arquivo de configuraçao do git
  - git config --list
  - Apagando  parmentos de configuração do git para eventual correção. git config --global --unset e digita o paramentro a ser pagado. ex: git config --global --uset user.name

##### Transfernindo arquivos do repositorio local para o GitHub

- git remote add origin "Cola o endereço do repositorio do GitHub"
- git remote -v [Lista os repositorios cadastrados
- git push origin master - empurra os arquivos para o repositorio do gitHub.

##### Resolvendo conflitos

> se um Arquivo que estiver no GitHub estiver com a atualização mais recente do que os arquivos que você estiver enviando para o GitHub, hverá um conflito de versões. Neste caso voce deverá baixar a versão que está no GitHub para o seu repositorio local e checar quais foram as modificações feitas e aceita-las ou corrigi-lás.
>
> Para puxar use o comando: git pull origin master.
>
> Qundo a alteração for na mesma linha acontece o erro de Merge Conflict.

- para clonar um repositorio
  - git clone e cole o endereço de repositorio desejado.









