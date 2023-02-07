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

