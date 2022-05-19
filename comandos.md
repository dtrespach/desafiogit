# Lista de comandos Git #

## Os comandos estão dispostos de forma "cronológica", ou seja, seguindo um passo a passo para criar o seu primeiro repositório no Github utilizando o Git ##



### Configuração inicial ###

**git config  --global user.name** configuração inicial do Git em sua máquina que define o **usuário** que irá manipular os arquivos;

**git config --global user.email** configuração inicial do Git em sua máquina que define o **e-mail** do usuário configurado anteriormente;

*(opcional)* **git config --list** mostra uma lista detalhada das configurações de **usuário** e **e-mail** ;

### Gerando chaves SSH para vincular com o Github ###

**ssh - keygen -t ed25519 -C "[seu_email@exemplo.com]()"** cria um par de chaves SSH, uma pública, que deve ser inserida em sua conta Github;

A chave pública, que estará na pasta **C:/Users/seunome/.ssh**  como **id_ed25519.pub**, deve ser adicionada na sua conta no Github, no menu *Settings / SSH and GPG keys / New SSH key*, cole o conteúdo da chave pública dentro do campo requerido e pronto, sua chave SSH já está vinculada a sua conta no Github.

*(opcional)* Caso queira que o SSH Agent gerencie  sua chave privada, use o comando:

**eval "$(ssh-agent  -s)"** irá retornar um *pid*, em seguida, aponte o *agent* para sua chave privada com o comando:

**ssh-add C:/Users/seunome/\.ssh/id_ed25519**

### Iniciando o Git ###

Com o *bash* aberto na pasta do seu projeto, use o comandos:

**git init**  como o nome do comando já define, inicia um repositório .git (oculto) com os metadados do Git na pasta pasta de trabalho do projeto;

**git add .** adiciona todos os arquivos da pasta do projeto para a área de *stage* ;

**git add "nome do arquivo"** adiciona o arquivo especificado para área de stage;

*(opcional)* **git status** mostra a situação dos arquivos que foram adicionados;

**git commit -m "mensagem"** adiciona os arquivos do *stage* para o repositório local com uma mensagem, identificando aquele *commit*;

**git branch -M **aponta o commit para a *branch* principal *main*;

Em seguida, crie um novo repositório no Github e  use o caminho SSH no comando abaixo:

**git remote add origin git@github.com:seuusuario/seurepositorio.git** 

**git push -u origin main** "empurra" todos os arquivos commitados para o repositório definido no comando anterior na *branch* principal (*main*);





