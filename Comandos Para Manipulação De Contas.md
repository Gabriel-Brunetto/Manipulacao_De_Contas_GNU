**Comandos para manipulação de contas**

  ***Comandos usados para manipulação de conta de usuários e grupos em sistemas GNU/Linux. Entre os assuntos descritos aqui estão adicionar usuários ao sistema, adicionar grupos, incluir usuários em grupos existentes, etc.
Os estilos não têm praticamente nada de HTML, eles têm o formato de ‘propriedade: valor’ e a maioria das propriedades pode ser aplicada à maioria das tags HTML.***

**Conteúdo:**
-adduser
-addgroup
-passwd
-gpasswd
-newgrp
-userdel
-groupdel
-lastlog
-last
-logname
-users
-groups


**adduser**

  <sub>Adiciona um usuário ou grupo no sistema. Por padrão, quando um novo usuário é adicionado, é criado um grupo com o mesmo nome do usuário. Opcionalmente o adduser também pode ser usado para adicionar um usuário a um grupo
Será criado um diretório home com o nome do usuário.  e este receberá uma identificação. A identificação do usuário (UID) escolhida será a primeira disponível no sistema especificada de acordo com a faixa de UIDS de usuários permitidas no arquivo de configuração /etc/adduser.conf. Este é o arquivo que contém os padrões para a criação de novos usuários no sistema.

adduser [opções] [usuário/grupo]

Onde:

usuário/grupo
Nome do novo usuário que será adicionado ao sistema.

opções, -disable-passwd
Não executa o programa passwd para escolher a senha e somente permite o uso da conta após o usuário escolher uma senha.

--force-badname
Desativa a checagem de senhas ruins durante a adição do novo usuário. Por padrão o adduser checa se a senha pode ser facilmente adivinhada.

--group
Cria um novo grupo ao invés de um novo usuário. A criação de grupos também pode ser feita pelo comando addgroup.

-uid [num]
Cria um novo usuário com a identificação [num] ao invés de procurar o próximo UID disponível.</sub>

**addgroup**

  <sub>Adiciona um novo grupo de usuários no sistema. As opções usadas são as mesmas do “adduser”.

addgroup [usuário/grupo] [opções]</sub>


**passwd**

  <sub>Modifica a parametros e senha de usuário. Um usuário somente pode alterar a senha de sua conta, mas o superusuário (root) pode alterar a senha de qualquer conta de usuário, inclusive a data de validade da conta, etc. Os donos de grupos também podem alterar a senha do grupo com este comando.

passwd [usuário] [opções]

Onde:

usuário
Nome do usuário que terá sua senha alterada.

opções, -e
Força a expiração de senha para a conta especificada.

-k
Somente altera a senha se a conta estiver expirada.

-x [dias]
Especifica o número máximo de dias que a senha poderá ser usada. Após terminar o prazo, a senha deverá ser modificada.

-i
Desativa a conta caso o usuário não tenha alterado sua senha após o tempo especificado por -x.

-n [dias]
Especifica o número mínimo de dias para a senha ser alterada. O usuário não poderá mudar sua senha até que [dias] sejam atingidos desde a última alteração de senha.

-w [num]
Número de dias antecedentes que o usuário receberá o alerta para mudar sua senha. O alerta ocorre [num] dias antes do limite da opção -x, avisando ao usuários quantos dias restam para a troca de sua senha.

-l [nome]
Bloqueia a conta do usuário [nome]. Deve ser usada pelo root. O bloqueio da conta é feito acrescentando um caracter a senha para que não confira com a senha original.

-u [nome]
Desbloqueia a conta de um usuário bloqueada com a opção -l.</sub>


**gpasswd**

  <sub>Modifica parametros e senha de grupo. Um usuário somente pode alterar a senha de seu grupo, mas o superusuário (root) pode alterar a senha de qualquer grupo de usuário, inclusive definir o administrador do grupo.

gpasswd [opções] [usuario] [grupo]

Onde:
usuário
Nome do usuário/grupo que terá sua senha alterada.

opções, -r usuario grupo
Remove a senha de grupo.

-R usuario grupo
Desativa o acesso do grupo usando o comando newgrp.

-a usuario grupo
Adiciona o usuário no grupo especificado.

-d usuario grupo
Apaga o usuário do gurpo especificado.</sub>

**newgrp**

  <sub>Altera a identificação de grupo do usuário. Para retornar a identificação anterior, digite exit e tecle Enter. Para executar um comando com outra identificação de grupo de usuário, use o comando “sg”.

newgrp - [grupo]

Onde:

Se usado, inicia um novo ambiente após o uso do comando newgrp (semelhante a um novo login no sistema), caso contrário, o ambiente atual do usuário é mantido.

grupo
Nome do grupo ou número do grupo que será incluído.</sub>


**userdel**
  <sub>Apaga um usuário do sistema. Quando é usado, este comando apaga todos os dados da conta especificado dos arquivos de contas do sistema.

userdel [-r] [usuário]

Onde:

-r
Apaga também o diretório HOME do usuário.</sub>


**groupdel**

  Apaga um grupo do sistema. Quando é usado, este comando apaga todos os dados do grupo especificado dos arquivos de contas do sistema.

groupdel [grupo]

Tenha certeza que não existem arquivos/diretórios criados com o grupo apagado através do comando find.</sub>


**lastlog**

  <sub>Mostra o último login dos usuários cadastrados no sistema. É mostrado o nome usado no login, o terminal onde ocorreu a conexão e a hora da última conexão. Estes dados são obtidos através da pesquisa e formatação do arquivo /var/log/lastlog. Caso o usuário não tenha feito login, é mostrada a mensagem ** Never logged in.

lastlog [opções]

Onde:

opções, -t [dias]
Mostra somente os usuários que se conectaram ao sistema nos últimos [dias].

-b [dias]
Mostra somente os usuários que se conectaram antes de [dias].

-u [nome]
Mostra somente detalhes sobre o usuário [nome].</sub>

**last**

  Mostra uma listagem de entrada e saída de usuários no sistema. São mostrados os seguintes campos na listagem:

Nome do usuário

Terminal onde ocorreu a conexão/desconexão

O hostname (caso a conexão tenha ocorrido remotamente) ou console (caso tenha ocorrido localmente).

A data do login/logout, a hora do login/down se estiver fora do sistema/ still logged in se ainda estiver usando o sistema

Tempo (em Horas:Minutos) que esteve conectado ao sistema.

Onde:

opções, -n [num]</sub>


**logname**

  <sub>Mostra seu login (username).

logname</sub>


**users**

  <sub>Mostra os nomes de usuários usando atualmente o sistema. Os nomes de usuários são mostrados através de espaços sem detalhes adicionais, para ver maiores detalhes sobre os usuários.</sub>


**groups**

  <sub>Mostra os grupos que o usuário pertence.</sub>


referência: https://www.guiafoca.org/guiaonline/iniciante/ch10.html
