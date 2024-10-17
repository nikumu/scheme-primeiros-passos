# Como instalar scheme ou mit-scheme no Ubuntu

`sudo apt update`

`sudo apt install mit-scheme`

Esta versão instalada do Ubuntu conhece o mit-scheme, enquanto a outra não.

`aptscheme`

# Como instalar DrScheme 5.0.2

Você pode tentar instalar a versão diretamente do Racket Team PPA

`sudo add-apt-repository ppa:plt/racket && sudo apt-get update`

depois disso instale-o com

`sudo apt-get install racket`

Isso será a versão 5.2.0-3 para o Ubuntu 11.10, no entanto.

>O pacote mit-scheme está disponível apenas para x64, o que significa que não aparecerá em instalações baseadas em ARM. 
