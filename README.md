# bootcamp-linux-do-zero
Entendendo o que é o Linux e suas funcionalidades

## O que é um Sistema Operacional?

O sistema operacional é um software, ou um conjunto de softwares, que tem a função de administrar ou genrenciar os recursos de um sistema. 

Esses recursos são: componentes de hardware, sistemas de arquivos, programas de terceiros, etc. 

_A principal função do sistema operacional é estabelecer uma interface entre o hardware e o usuário._

**O que é o Kernel ou núcleo do sistema operacional?**

Resumidamente, o Kernel é a ponte entre o usuário e o hardware. O kernel compõe a parte central do SO e responde por tarefas cruciais, como:

1. Estabelecer a camada de abstração de baixo nível (linguagem de máquina) com o hardware;
2. Gerenciar recursos como processador, memória RAM, sistemas de arquivos e dispositivos de entrada e saída;
3. Gerenciais processos (execução) de programas;
4. Gerenciar o uso de dispositivos, memória do sistema e chamadas dos programas, definindo quais têm prioridade.

![funcionamento-do-kernel](CPU.png)

_Sistemas operacionais domésticos mais utilizados:_
* Microsoft Windows
* Mac OS
* Linux

_Vídeo:_ [Most Popular Operating Systems [Desktops & Laptops] 2003-2019](https://youtu.be/eJuvKn5j_kE)

## O que é o Linux?

O Linux é um dos sistemas operacionais mais populares e é amplamente utilizado no segmento de __servidores__ e por __desenvolvedores de software__. 

Ainda existe um grande espaço para crescimento no segmento de computadores pessoais.

O kernel do Linux começou a ser __desenvolvido por Linus Torvalds__ em 1991 inspirado no Unix, um outro sistema operacional criado nos anos 70. O Desenvolvimento inicial do kernel do Linux começou com Linus ainda quando estava na faculdade em Helsinki, na Finlândia. 

O Linux, mais especificamente o kernel do sistema operacional, não é suportado por uma empresa individual, mas por uma comunidade internacional de desenvolvedores. O kernel do Linux está disponível gratuitamente e pode ser usado por qualquer pessoa, sem restrições.

O kernel do Linux é mantido pela [Linux Foundation](https://linuxfoundation.org/), que é uma organização sem finslucrativos. Para manter o kernel atualizado e implementar melhorias, a fundação é mantida por doações de grandes empresas que utilizam o Linux em seus produtos ou serviços.

### __O que são distribuições?__

Uma distribuição Linux é um pacote que consiste em um kernel Linux, mais uma seleção de aplicativos mantidos por uma empresa ou comunidade de usuários. O objetivo de uma distribuição é otimizar o kernel e os aplicativos que rodam no sistema operacional para um determinado tipo de uso ou grupo de usuários.

### __Sistemas Embarcados__

Os sistemas embarcados são uma combinação de hardware e software projetados para cumprir uma função específica de um sistema maior. 

Normalmente fazem parte de outros dispositivos e ajudam a controlá-los. Podem ser encontrados em aplicações automotivas, médicas e até militares.

O Android é um sistema operacional móvel desenvolvido principalmente pela Google. A empresa inicialmente criou um sistema operacional destinado a rodar em câmeras digitais. 

## Diferenças entre o Linux Desktop e Linux Server

O modelo cliente-servidor é uma estrutura de aplicação que distribui as tarefas e cargas de trabalho entre os fornecedores de um recursos ou serviço, designados como servidores, e os requerentes dos serviços, designados como clientes.

![cliente-servidor](cliente-servidor.png)

## Acesso Remoto via Linux

Como fazer o acesso remoto de uma máquina virtual linux via SO Linux?

É muito simples! Basta digitar o comando:

> ssh [nome de usuário]@[número do ip]

Para localizar o número do ip que você deseja fazer o acesso remoto, informe o comando no terminal:

> ip a

Se estiver tudo certo, você conseguirá realizar o acesso remoto sem problemas. Muito fácil né? ;)

## Navegando pelo sistema de arquivos

> pwd - informa em qual diretório você está

> cd - change directory ou mudar de diretório

> cd .. - sair do diretório

> / - diretório raiz

> /~/ - usuário sem permissões de administrador

> /#/ - usuário com permissões de administrador

> ls - lista os arquivos que estão dentro de um diretório

> cd ../ - sai do diretório atual e muda para o novo diretório

> cd / - sair de todos os diretórios e voltar para o diretório raiz

> cat - mostra o conteúdo de um arquivo texto

## Filtrando a exibição de arquivos

> ls | more - quando uma lista grande precisa ser exibida mas o sistema não possui barra de rolagem, assim é possível ver a lista completa

> ls [letra]* - lista os arquivos que iniciam com essa letra

> ls ?* - para especificar o caracter que se está buscando

> ls arquivo[1-3]* - lista 3 arquivos em sequência

> ls arquivo [2,5]* - lista apenas os arquivos na posição informada pelo parâmetro

> ls arquivo [^2, 5]* - não lista os arquivos nas posições 2 e 5

> ls arquivo [^3-5]* - não exibe os arquivos nas posições 3 até 5

## Localizando arquivos


> ls /nome do diretório - lista os arquivos que estão dentro do diretório referido

> ls /nome do diretório/ nome do diretório - lista os arquivos que estão no último diretório referido 

> ls /nome do diretório/nome do diretório/letra* - lista os arquivos dentro do último diretório que começam com uma letra específica

> ls -a - localiza arquivos ocultos

> find -name [nome do arquivo]* - busca um arquivo pelo nome dentro do diretório atual

## Criando diretórios

> mkdir /local - cria um diretório no local indicado
 
## Excluindo arquivos e diretórios

> rmdir - exclui diretórios

> rm - exclui arquivos

> rm nome do arquivo* - exclui todos os arquivos que tenham o mesmo nome 

> rm- rf - exclui todos os arquivos de um diretório

> rfv - recursive force verbose - remove arquivos e diretórios e explica o que está acontecendo enquanto a exclusão acontece

> rfvi - pede permissão para excluir

## Obtendo ajuda

> [comando] --help - lista comandos úteis do terminal

> man [comando] - lista comandos úteis

> -R - abre o que está dentro de cada uma das pastas que estão dentro de um diretório

## Executando tarefas administrativas como root

O comando usado para realizar as tarefas administrativas como usuário root é **sudo**.

Digitando esse comando, é possível ter acesso as configurações da utilização do comando sudo. 

> cat /etc/sudoers

## Logando como usuário root

**Criando senha para o usuário root**

> sudo passwd root

**Para logar como super usuário, digite o comando:**

> su

**Para trocar de usuário**

> su [nome do usuário]

## Liberando acesso remoto do usuário root

O comando abaixo, abre o arquivo onde a gente pode visualizar as configurações para liberar o acesso remoto ao usuário root:

> cat /etc/ssh/sshd_config

O **nano** é um editor de texto que pode ser utilizado via terminal Linux. 

O comando abaixo, permite que a gente abra o arquivo onde podemos visualizar as configurações para liberar o acesso remoto ao usuário root a partir desse editor de texto.

> nano /etc/ssh/sshd_config

Porém a gente não vai conseguir editar esse arquivo porque é um arquivo 'unwritable', ou seja, não editável.

Para corrigir isso é muito simples. Isso aconteceu porque não temos permissão de usuário root. Portanto, basta digitar a mesma linha de comando mas acrescentando o comando **sudo**. Desta forma:

> sudo nano /etc/ssh/sshd_config

Ou poderia entrar diretamente trocando para o usuário root.

**Depois disso, é preciso reiniciar o serviço ssh.**

> systemct1 status sshd [para visualizar quem está acessando o sistema]

> systemct1 restart sshd [para reiniciar o serviço]

## Trabalhando com arquivos de texto

**Vi - editor de texto a partir do terminal.**

Para abrir um arquivo ou criar um novo arquivo, basta digitar a seguinte linha de comando:

> vi [nome do arquivo de texto]

Para inserir conteúdo dentro do arquivo de texto a partir do vi:

> tecla i para abrir o modo de inserção de texto

Para fechar o modo de inserção:

> tecla esc para fechar o modo de inserção de texto

Para salvar e sair do editor:

> :wq

w - write
q - quit

Para ler o que foi criado dentro desse arquivo, é só digitar o comando:

> cat + nome do arquivo

**Nano - editor de texto a partir do terminal**

O Nano é mais fácil de ser usado pois ele dá para o usuário a sugestão de como as teclas de atalho devem ser usadas. Para iniciantes, é o editor de texto a partir do terminal mais recomendado. 

## Histórico de comandos

É interessante saber como verificar o histórico de comandos para verificar o que o(s) usuário(s) estão aprontando. :P

Comando **history** - armazena o histórico de comandos de um usuário. 

Para utilizar esse comando, basta digitar no terminal o seguinte:

> [nome do usuário] + history

Para aproveitar um comando que já foi utilizado:

> ! + o número em que esse comando aparece

Para aproveitar o último comando utilizado:

> !!

Executar um comando que não sei todas as letras:

> ex.: !?dat?

Consulta para saber todas as vezes que uma palavra foi utilizada, independente do parâmetro que foi utilizado:

> history | grep "palavra"

trocar uma variável de ambiente:

> export HISTTIMEFORMAT="%c "

trocar o parâmetro do terminal para que um comando não seja armazenado:

> set +o nome do comando

Os comandos utilizados não serão armazenados, mas o parâmetro que faz isso acontecer será armazenado. Portanto, ao verificar a atividade desse usuário que fez essa troca de parâmetro, poderá ser verificada essa mudança. 

Para desfazer essa mudança, basta utilizar o comando:

> set -o nome do comando

Armazenar um número exato de comando de um usuário:

> cat .bashrc

Para editar o arquivo:

> nano .bashrc 

Mudar o parâmetro do HISTSIZE para 50, por exemplo. 

Só serão armazenados os cinquenta últimos comandos utilizados pelo usuário.

Histórico de todos os comandos utilizados pelo usuário:

> history -w

Esse comando não retorna nada. Esse histórico estará na pasta do usuário chamada .bash_history

## Criando e excluindo usuários

Criando usuário:

> useradd nomedousuario

Excluindo usuário:

> userdel -r -f nomedousuario

Criando usuário, pasta e cadastrar o nome completo desse usuário:

> useradd nomedousuario -m -c "Nome Completo do Usuário"

Criando senha para o novo usuário:

> passwd nomedousuario

Indicando qual o shell* que o novo usuário vai utilizar:

***Shell é um programa que vai ter acesso ao kernel do sistema operacional**

> chsh (change shell) -s /bin/bash/nomedousuario

Essa configuração foi necessária porque na hora que o usuário foi criado o shell não foi especificado. 

Deletando o usuário criado:

> userdel -r -f nomedousuario

Dessa forma, é possível ter certeza de que o usuário foi excluído. 

**Indicando o bash do usuário no momento em que este está sendo criado:**

> useradd nomedousuario -m -c "Nome do Usuário" -s /bin/bash

Criar senha do usuário:

> passwd nomedousuario

## Editando informações do usuário

Criando acesso para o usuário durante um período pré-estabelecido:

> useradd guest -c "Convidado" -m -e 12/02/2023

Para realizar alterações no usuário:

> usermod

Para o usuário cadastrar a própria senha e definir uma data de expiração da senha:

> passwd nomedousuario -e

Consultar quanto usuários há no sistema:

> cat etc/passwd

> usermod guest -c "Convidado Especial"

## Shell Script - Criando usuários em lote

Criando usuário com senha encriptada

> useradd convidado1 -c "Convidado Especial" -s /bin/bash -m-p $(openssl passwd -crypt Senha123)

Criar usuários com senha definida

> mkdir /scripts

> nano criar_user.sh

Iniciar arquivo de texto assim:
>#!/bin/bash

Script para criar usuários com a possibilidade de criar a própria senha:
> useradd guest10 -c "Usuário Convidado" -s /bin/bash -m -p $(openssl passwd -cript Senha123)

> passwd guest10 -e

Finalize o arquivo com

> echo "Finalizado!!!"

Para conseguir editar o arquivo .sh, escreva o parâmetro e execute:

>chmod +x criar_user.sh

Para acessar o arquivo, escreva:

> ./criar_user.sh

## Adicionando usuários a grupos

Criando usuário

> useradd mariana -c "Mariana dos Anjos" -m -s /bin/bash -p $(openssl passwd -crypt Senha123)

Checar os grupos que estão no sistema:

> cat /etc/group

Adicionando ao grupo sudoers (adm,sudo):

> usermod -G adm,sudo mariana

Agora o usuário Mariana tem privilégios de administrador, mas sempre que quiser criar uma pasta ou usuário, ela terá que usar o comando sudo, porque embora tenha privilégio de administrador, não é um usuário root.

## Criando novos grupos

Criando grupos:

> groupadd GRP_ADM

> groupadd GRP_VEN

Adicionando usuários a esses grupos:

> useradd rodrigo -c "Rodrigo Silva" -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -GRP_ADM

> useradd debora -c "Débora Silva" -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -GRP_ADM

> useradd daniel -c "Daniel Silveira" -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -GRP_VEN

> useradd maisa -c "Maisa Ribeiro" -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -GRP_VEN

Para checar os usuários que foram adicionandos aos grupos:

> cat /etc/group

Adicionando um usuário que já foi criado a um grupo:

> usermod -G GRP_VEN joao

Excluir um usuário de um grupo e transferi-lo para outro:

> usermod -G GRP_VEN mariana

Para checar se a mudança ocorreu:

> cat /etc/group

Mariana saiu dos grupos que ela estava e ficou apenas no grupo indicado na linha de comando. Mas se a gente quisesse que ela permanecesse nos grupos em que estava, o comando que a gente precisaria dar seria:

> usermod -G adm,sudo,GRP_VEN mariana

Mas e se a gente quisesse tirar a Mariana só do grupo sudo? Existe um comando específico para isso:

> gpasswd -d mariana sudo

## Conectando o sistema de permissões

r - read </br>
w - write </br>
x - execution

1ª coluna - dono 4</br> 
2ª coluna - grupo 2</br> 
3ª coluna - outros 1 </br>
Nenhuma permissão - 0

**Criando permissões**

Trocando o dono de um diretório e o grupo que pode acessar esse diretório:

> chown debora:GRP_ADM /adm/

Essa ação só é possível se você estiver logado no sistema como usuário root ou utilizando o comando sudo.

> chown mariana:GRP_VEN /ven/

## Alterando as permissões de um diretório - arquivo

> chmod 750 /adm/

Cada número corresponde a uma coluna. 

Adicionando permissão de execução a um arquivo

> chmod +x date.sh

## Gerenciamento de Pacotes Debian / Ubuntu

Baixo nível - a nível do sistema. Menos amigável com o usuário.

> apt-get

Ferramenta mais moderno. Interação com o usuário mais amigável

> apt

Listar atualizações disponíveis

> apt list --upgradable

Buscar atualizações de uma aplicação específica.

> Ex.: apt search samba

Comando para fazer downloads de arquivos a partir do terminal:

> wget

Para descompactar um arquivo zipado:

> unzip

Para remover programas instalados:

> apt remove 

Link de todos os repositórios oficiais do ubuntu

> apt edit-sources

## Atualização do Sistema Operacional

Vai fazer a atualização sem perguntar nada

> apt upgrade -y























