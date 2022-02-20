# Editando o VIM
Em busca de melhorar a produtividade irei começar a usar o vim como editor,
para isso será necessário modificar algumas coisas, esse arquivo será o 
passo a passa de como fazer essas modificações.

## VIMRC

Primeira coisa que devemos fazer é saber onde está o arquivo vimrc, para isso
iremos, com o vim aberto, escrever

: help vimrc

diferente do que é falado no arquivo, não tenho o vimrc no home, ele está em

/etc/vim

Mas iremos criar o novo arquivo vimrc na home, para isso basta usar 

vim ~/.vimrc

nesse novo arquivo iremos criar os seguinte comandos:

" ativar sintaxe colorida
syntax on

" ativar indentação automática
set autoindent

" ativa indentação inteligente, o Vim tentará adivinhar
" qual é a melhor indentação para o código quando você
" efetuar quebra de linha. Funciona bem para linguagem C
set smartindent

" por padrão o vim armazena os últimos 50 comandos que você
" digitou em seu histórico. Eu sou exagerado, prefiro armazenar
" os últimos 5000
set history=5000

" ativar numeração de linha
set number

" destaca a linha em que o cursor está posicionado
" ótimo para quem não enxerga muito bem
set cursorline

" ativa o clique do mouse para navegação pelos documentos
set mouse=a

" ativa o compartilhamento de área de transferência entre o Vim
" e a interface gráfica
set clipboard=unnamedplus

" converte o tab em espaços em branco
" ao teclar tab o Vim irá substutuir por 2 espaços
set tabstop=2 softtabstop=2 expandtab shiftwidth=2

" ao teclar a barra de espaço no modo normal, o Vim
" irá colapsar ou expandir o bloco de código do cursor
" foldlevel é a partir de que nível de indentação o
" código iniciará colapsado
set foldmethod=syntax
set foldlevel=99
nnoremap <space>


Vamos agora falar sobre os plugins, antigamente era necessário instalar eles
de forma manual, agora é possível fazer isso de forma mais automática,
na pasta *vim* temos um diretório *pack* nele teremos todos os plugins. 

Para ficar mais organizado os plugins que irei instalar estão na pasta 

git-plugins

Vale a pena lembrar que, a pasta start significa que os plugins que estão nelas
serão recarregados assim que o vim for ativo.

# Instalando os plugins

## Instalando o primeiro plugin
Iremos instalar o primeiro plugin, que será mostrará a página principal do vim.
Para isso no diretório start iremos clonar o seguinte repositório:

https://github.com/mhinz/vim-startify

## Instalando plugins para a parte visual

### Tema dracula
Vamos começar com o tema, nesse caso, como gosto do tema do dracula, então ele que irei usar

para isso iremos clonar o seguinte repositório no diretório start

$ git clone https://github.com/dracula/vim.git dracula

após isso é necessário fazer algumas mudanças no arquivo *vimrc*, adicione as
seguintes linhas após a 
[...] 
nnoremap <space>

packadd! dracula
syntax enable
colorscheme dracula

### Identação

git clone https://github.com/Yggdroot/indentLine


# Comando importantes do vim

Em relação a navegação podemos usar o módulo normal do vim para poder navegar.
Dessa forma as teclas: *hjkl* são usadas para navegação.
 * h - move para a esquerda
 * j - move para baixo
 * k - move para cima
 * l - move para direita
 
 Ainda no modo normal é possível deslocar para o inicio ou final da linha usando
 o *shift+A* para o final e o *shift+i* para o começo.

 Também possível navegar por palavras, dessa forma é possível tanto usar a letra *B* ou *W* vai para o começo da palavra
 já ao usar o *E* vamos para o final da palavra, para todos esses casos podemos usar o *shift* para fazer a navegação.
Para que seja possível ir ao começo do arquivo podemos usar o *g* e para ir no final *shift+g*.

Para poder abrir um outro arquivo com o vim aberto:

*: e ~/nome*

Para voltar a ação anterior é só usar o *U* já o *ctrl+u* refaz a ação.

Para poder copiar podemos usar *y* e para colar o *p*. 
Para procurar palavra no arquivo é só usar */* e para poder navegar é só usar *n*
ou *shift+n* 

