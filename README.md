# A linguagem Scheme

</a><img src="https://upload.wikimedia.org/wikipedia/commons/3/39/Lambda_lc.svg" min-width="380px" max-width="200px" width="175px" align="right">   
             
### 01. Introdução
           
Como o paradigma funcional é algo que está em alta atualmente, resolvi escrever esse artigo ilustrando a eficiência de uma linguagem funcional, apresentando as principais características e claro, alguns exemplos de códigos. Primeiramente, é bom efatizar que Existem dois padrões que definem a linguagem Scheme: o padrão oficial IEEE e um outro, mais popular chamado “Revisedn Report on the Algorithmic Language Scheme”, abreviado como RnRS, que atualmente se encontra na versão 6. Para os exemplos mostrados aqui, usarei a IDE DrScheme, que pode ter obtido em: <https://download.racket-lang.org/>

Scheme é uma linguagem funcional, desenvolvida na década de 1970 por Gerald Jay Sussman e Guy L. Steele, projetada para ser uma versão simples de Lisp. Scheme é mais simples por conter um pequeno grupo de regras e ter a possibilidade de fazer composições dessas regras. A ausência de restrições, torna Scheme numa liguagem muito poderosa e flexível. Logo, não precisa incorporar novas funções para contornar inconvenientes causados pela existência de alguma restrição na linguagem. Com o tempo, Scheme também se tornou uma escolha popular em ambientes acadêmicos, especialmente no ensino de ciência da computação.


### 02. Aspectos Gerais

A primeira impressão que temos, é que Scheme funciona como uma calculadora, onde escrevemos uma expressão e o interpretador nos mostra o resultado. Isso, porque a linguagem oferece um dispositivo chamado “REPL” (Read-Eval-Print Loop). O REPL é um programa simples e interativo que lê expressões ou trechos de programa, avalia (ou executa) e imprime o resultado. Na prática, a experiência de usar o REPL é semelhante a de interagir com um terminal. Sempre que você digitar um comando, o REPL vai imprimir o valor de retorno do comando.

Um exemplo de hello world em Scheme:
```~~~scheme
(display "hello, world!")
```
simples, não ?

Nessa linguagem, as expressões utilizam notação pré-fixa, em que o operador aparece antes dos operandos. Este tipo de notação tem uma grande vantagem que é a qualidade expressiva. Existem regras únicas a serem utilizada em qualquer expressão, evitando possíveis ambiguidades. 

Comentários em Scheme são delimitados por `;` e tudo que estiver nessas linhas será ignorado pelo compilador.

Exemplo:
```~~~scheme
;Imprimindo múltiplos valores
(display "The result is: ")
(display (+ 3 4))
```
Saída:`The result is: 7`

### 03. Funções

Para calcular o valor de uma função, escrevemos:
```~~~scheme
(f x)
```
ao invés de `f(x)`, normalmente usada na matemática. Se a função tiver muitos parâmetros, como `f(x,y,z)`, escrevemos:
```~~~scheme
(f x y z)
```
No exemplo a seguir, o operador aritmético da adição surge primeiro, seguido dos operandos 5 e 6, que em outras notações, isso seria `5+6`, ou `soma(5,6)`
```~~~scheme
(+ 5 6)
```
nessas expressões compostas, apresentam-se rodeadas por parênteses e, dentro destes, aparece em primeiro lugar, o operador. A regra de cálculo de uma expressão composta alguns passos, onde primeiramente, calcula-se cada um dos operadores da expressão e em seguida, aplica-se o operador aos operandos calculados.

Do cálculo dos operandos `5` e `6`, resultam respectivamente, os valores `5` e `6`. Aplicando-lhes o operador `+`, resultando no valor `11`.

Tudo que escrevemos em Scheme é chamado de expressão, que podem ser classificadas em dois tipos: átomos e listas. Os átomos podem ser numerais, textos ou símbolos.

Os números são dados simples, que representam e devolvem o próprio valor. Por exemplo, o número `10`, quando integrado a uma expressão, devolve o valor `10`.

### 04. Listas

Uma lista, por sua vez, é uma sequência de expressões entre parênteses. Quando o interpretador recebe uma lista, tenta interpretá-la como a aplicação de um procedimento. Para definir um procedimento, usamos o operador define e podemos aplicá-lo aos argumentos para ver seu funcionamento. Por exemplo, usando a sintaxe básica a seguir:
```~~~scheme
(define foobar 4)
```
O valor `4` é associado a `foobar`. Também podemos dizer que a variável `foobar` tem valor `4`. A partir daí, quando calculamos o valor da expressão `foobar`, o resultado será `4`. Um outro exemplo de hello world, dessa vez como um procedimento :
```~~~scheme
;procedimento de hello world
   (define hello
      (display "hello !"))
```
Para que o Scheme retorne o símbolo, e não seu valor, precisamos “citá-lo”:
```~~~scheme
(quote foobar)
```
Uma lista iniciando com quote é uma forma especial em Scheme, que tem regras específicas para avaliação. A forma especial quote retorna seu argumento, sem que ele seja avaliado.
```~~~scheme
(car '(a b c))
```
Onde car retorna o primeiro elemento de uma lista
