{% set warning_icon = '<span class="glyphicon glyphicon-exclamation-sign" style="color: red;" aria-hidden="true" data-toggle="tooltip" title="An error is expected when you run this command!" ></span>' %}

# Vamos começar com o Python

Vamos contar o que é Python. Python é uma linguagem de programação muito popular que pode ser usada para criar sites, jogos, software científicos, gráficos e muito, muito mais.

O Python foi criado na década de 1980 e seu principal objetivo é ser legível por seres humanos (e não apenas pelas máquinas!). Por isso ele parece mais simples que outras linguagens de programação, mas não se preocupe - o Python também é muito poderoso!

# Introdução ao Python

> Parte deste capítulo é baseada no tutorial da Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).

Vamos escrever um pouco de código!

## Interpretador de Python

Para começar a trabalhar com Python, precisamos abrir uma * linha de comando* no computador. Você provavelmente já sabe como fazer isso - aprendeu no capítulo [ Introdução à Linha de Comando ](../intro_to_command_line/README.md).

Assim que estiver pronta, siga as instruções abaixo.

Queremos abrir um console do Python, então digite `python` no Windows ou `python3` no Mac OS/Linux e pressione `enter`.

{% filename %}command-line{% endfilename %}

    $ python3
    Python 3.6.1 (...)
    Digite "ajuda", "direitos autorais", ou "licença" para mais informações.
    >>>


## Seu primeiro comando em Python!

Depois de executar o comando Python, o prompt mudou para `>>>`. Isso significa que por enquanto nós só podemos utilizar comandos na linguagem Python. Você não precisa digitar `>>>` - o Python fará isso por você.

Se a qualquer momento você quiser sair do console do Python, apenas digite `exit()` ou use o atalho `Ctrl + Z` no Windows e `Ctrl + D` no Mac ou Linux. Então você não vai mais ver o `>>>`.

Por enquanto, não queremos sair do console do Python. Queremos saber mais sobre ele. Vamos começar digitando um pouco de matemática, como `2 + 3`, e clicar no `Enter`.

{% filename %}command-line{% endfilename %}

```python
>>> 2 + 3
5
```

Legal! Viu como a resposta apareceu? O Python sabe matemática! Você pode tentar outros comandos como:

- `4 * 5`
- `5 - 1`
- `40 / 2`

Brinque um pouco com isso e depois volte aqui. :)

Como você pode ver, o Python é uma ótima calculadora. Se você está se perguntando o que mais você pode fazer…

## Strings

Que tal o seu nome? Digite seu primeiro nome entre aspas, desse jeito:

{% filename %}command-line{% endfilename %}

```python
>>> "Maria"
'Maria'
```

Você acabou de criar sua primeira *string*! Uma *string* é uma sequência de caracteres que pode ser processada pelo computador. Ela deve sempre começar e terminar com o mesmo caractere. Este caractere pode ser aspas duplas (`"`) ou simples (`'`) (não há nenhuma diferença!). Elas dizem ao Python que o que está entre elas é uma string.

Strings podem ser unidas. Tente isto:

{% filename %}command-line{% endfilename %}

```python
>>> "Maria " + "Silva"
'Maria Silva'
```

Legal, hein? Para ver seu nome em letras maiúsculas, basta digitar:

{% filename %}command-line{% endfilename %}

```python
>>> "Maria".upper()
'MARIA'
```

Você acabou de usar a **função** `upper` na sua string! Uma função (como `upper()`) é um conjunto de instruções que o Python tem que realizar em um determinado objeto (`"Maria"`) sempre que você o chamar.

Se você quer saber o número de letras contidas em seu nome, há uma **função** para isso também!

{% filename %}command-line{% endfilename %}

```python
>>> len("Maria")
5
```

Talvez você esteja se perguntando porque algumas vezes chamamos funções com um `.` depois de uma string (como `"Maria".upper()`) e outras vezes primeiro chamamos a função e colocamos a string entre parênteses. Bem, em alguns casos, funções pertencem a objetos -- como `upper()`, que só pode ser utilizada em strings. Nesse caso, nós chamamos a função de **método**. Em outras vezes, funções não pertencem a nada específico e podem ser usadas em diferentes tipos de objetos, assim como `len()`. É por isso que nós estamos fornecendo `"Ola"` como um parâmetro para a função `len`.

### Sumário

OK, chega de strings. Até agora, você aprendeu sobre:

- **o prompt** -- digitar comandos (códigos) no interpretador de Python resulta em respostas em Python
- **números e strings** -- no Python, números são usados para matemática e strings, para objetos de texto
- **operadores** -- como `+` e `*`, combinam valores para produzir um novo valor
- **funções** -- como `upper()` e `len()`, executam ações nos objetos.

Esse é o básico de todas as linguagens de programação que você pode aprender. Pronta para algo mais difícil? 

Apostamos que sim! :)

## Erros

Vamos tentar algo novo. Será que conseguimos saber a extensão de um número da mesma forma que descobrimos a dos nossos nomes? Digite `len(304023)` e clique `Enter`:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> len(304023)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```

Temos nosso primeiro erro! O ícone {{ warning_icon }} é a forma que o Python tem para avisar que o código que você está prestes a executar não vai funcionar conforme o esperado. Cometer erros (inclusive intencionalmente) é uma parte importante da aprendizamgem!

Nossa primeira mensagem de erro nos diz que objetos do tipo "int" (inteiros, naturais) não têm comprimento algum. Então o que podemos fazer agora? Podemos escrever nosso número como string? Strings têm comprimento, certo?

{% filename %}command-line{% endfilename %}

```python
>>> len(str(304023))
6
```

Funcionou! Usamos a função `str` dentro da função `len`. A função `str ()` converte tudo para strings.

- A função `str` converte as coisas em **strings**
- A função `int` converte as coisas em **números inteiros**

## Variáveis

**Variáveis** são um conceito importante em programação. Uma **variável** é apenas um nome que você atribui a alguma coisa de tal forma que possa usá-lo mais tarde. Os programadores usam essas **variáveis** para armazenar dados, para tornar seus códigos mais legíveis e para não ter que se lembrar a todo momento o que são certas coisas.

Digamos que queremos criar uma nova **variável** chamada `nome`:

{% filename %}command-line{% endfilename %}

```python
>>> nome = "Maria"
```

Digitamos: nome igual Maria.

Como você deve ter percebido, a última linha de código não retornou nada como nos exemplos anteriores. Então como vamos saber se a variável realmente existe? Basta digitar `nome` e clicar `Enter`:

{% filename %}command-line{% endfilename %}

```python
>>> nome
'Maria'
```

Uhuuu! Sua primeira variável! :) Você sempre pode mudar o valor dela:

{% filename %}command-line{% endfilename %}

```python
>>> nome = "Sonja"
>>> nome
'Sonja'
```

Incrível, né? Claro, variáveis podem ser qualquer coisa, então podem ser números também! Tente isso:

{% filename %}command-line{% endfilename %}

```python
>>> a = 4
>>> b = 6
>>> a * b
24
```

E se digitarmos errado o nome da variável? Você consegue imaginar o que aconteceria? Vamos tentar!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> cidade = "Londres"
>>> cdiade
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'cdiade' is not defined
```

Um erro! Como você pode ver, o Python tem diferentes tipos de erros e este é chamado **NameError**. O Python mostrará esta mensagem de erro se você tentar usar uma variável que ainda não foi definida. Se você encontrar esse erro mais tarde, confira no seu código se você não digitou errado o nome de uma variável.

## A função print

Tente o seguinte:

{% filename %}command-line{% endfilename %}

```python
>>> nome = 'Maria'
>>> nome
'Maria'
>>> print(nome)
Maria
```

Quando você digita `nome`, o interpretador de Python responde com a *representação* da variável 'nome' na forma de string, que é sequência de letras **M-a-r-i-a**, entre aspas simples. Quando você disser para o Python `print(name)`, ele vai "imprimir" o conteúdo da variável na tela sem as aspas, que é mais bonitinho. :)

Como veremos mais tarde, `print()` também é útil quando queremos imprimir algo dentro de funções ou quando queremos imprimir algo em várias linhas.

## Listas

Além de strings e números inteiros, o Python tem muitos tipos diferentes de objetos. Agora vamos apresentar um chamado **lista**. **Listas** são exatamente o que você imagina: objetos que são listas de outros objetos. :)

Vá em frente e crie uma lista:

{% filename %}command-line{% endfilename %}

```python
>>> []
[]
```

Sim, esta é uma lista vazia. Não é muito útil, né? Vamos criar uma lista de números de loteria. Para não precisar repetir o código o tempo todo, vamos atribuí-la a uma variável:

{% filename %}command-line{% endfilename %}

```python
>>> loteria = [3, 42, 12, 19, 30, 59]
```

Legal, criamos uma lista! O que podemos fazer com ela? Vamos ver quantos números de loteria ela tem. Você tem ideia de qual é a função que deve usar para isso? Você já aprendeu ;)

{% filename %}command-line{% endfilename %}

```python
>>> len(loteria)
6
```

Sim! `len()` pode te dizer o número de elementos que fazem parte de uma lista. Uma mão na roda, né?

Como podemos adicionar elementos na lista?

Para adicionar elementos à sua lista, digite o seguinte comando:

{% filename %}command-line{% endfilename %}

```python
>>> loteria.append(199)
>>> print(loteria)
[59, 42, 30, 19, 12, 3, 199]
```

Se você quiser ver apenas o primeiro número da lista, pode usar **índices**. Um índice é o número que diz onde na lista um item está. Programadores preferem começar a contar a partir do zero, então o primeiro objeto em sua lista está no índice **0**, o segundo no 1 e assim por diante. Tente isso:

{% filename %}command-line{% endfilename %}

```python
>>> print(loteria[0])
59
>>> print(loteria[1])
42
```

Como você pode ver, podemos acessar diferentes objetos na lista usando o nome da lista e o índice do objeto entre colchetes.

Você pode encontrar uma lista de todos os métodos disponíveis neste capítulo na documentação do Python: https://docs.python.org/3/tutorial/datastructures.html

## Dicionários

Um **dicionário** é similar a uma lista, mas para acessar seus valores você usa uma chave ao invés de um índice. Uma chave pode ser qualquer string ou número. A sintaxe para definir um dicionário vazio é:

{% filename %}command-line{% endfilename %}

```python
>>> {}
{}
```

Você acabou de criar um dicionário vazio. Uhuuu! :)

Agora escreva o seguinte comando (e tente colocar suas próprias informações):

{% filename %}command-line{% endfilename %}

```python
>>> participante = {'nome': 'Maria', 'cidade': 'Londres', 'numeros_favoritos': [7, 42, 92]}
```

Com esse comando, você criou uma variável chamada `participante` com três pares de chave-valor:

- A chave `nome` aponta para o valor `'Maria'` (um objeto `string`),
- a chave `cidade` aponta para `'Londres'` (outra `string`),
- e a chave `numeros_favoritos` aponta para `[7, 42, 92]` (uma `list` de três números).

Você pode verificar o conteúdo de chaves individuais com a sintaxe:

{% filename %}command-line{% endfilename %}

```python
>>> print(participante['nome'])
Maria
```

É similar a uma lista, mas você não precisa lembrar o índice - apenas o nome.

Você deve estar se perguntando quando deve usar um dicionário ou uma lista, certo? Boa pergunta! A resposta rápida é:

- Você precisa de uma sequência ordenada de itens? Use uma lista.
- Você precisa associar valores a chaves para poder procurá-los eficientemente (pela chave) mais tarde? Use um dicionário.

Dicionários, assim como listas, são *mutáveis*. Isso significa que eles podem ser alterados depois de criados. Você pode adicionar um novo par chave-valor a um dicionário depois de ele ser criado, por exemplo:

{% filename %}command-line{% endfilename %}

```python
>>> participante['linguagem_favorita'] = 'Python'
```

Espero que esteja fazendo sentido até agora :)

Pronta para mais diversão com dicionários? Pule para a próxima linha para aprender mais coisas incríveis.

Você pode mudar o valor associado a uma chave já criada no dicionário. Digite:

{% filename %}command-line{% endfilename %}

```python
>>> participante['cidade'] = 'Paris'
>>> participante
{'cidade': 'Paris', 'linguagem_favorita': 'Python', 'nome': 'Maria'}
```

Agora, o valor da chave `'cidade'` foi alterado de `'Londres'` para `'Paris'`.

Emocionante? Uhu! Você acabou de aprender outra coisa incrível.  :)

### Sumário

Incrível! Agora você sabe muito sobre programação. Nesta última parte você aprendeu sobre:

- **erros** -- agora você sabe como ler e entender mensagens de erro que aparecem quando o Python não entende um comando que você deu;
- **variáveis** -- nomes para objetos que permitem que você programe facilmente e deixam seu código mais legível;
- **listas** -- listas de objetos armazenados em uma ordem específica;
- **dicionários** - objetos armazenados como pares chave-valor.

Animada para a próxima parte? :)

## Compare coisas

Grande parte da programação consiste em comparar coisas. O que é mais fácil comparar? Números, é claro. Vamos ver como isso funciona:

{% filename %}command-line{% endfilename %}

```python
>>> 5 > 2
True
>>> 3 < 1
False
>>> 5 > 2 * 2
True
>>> 1 == 1
True
>>> 5 != 2
True
```

Demos ao Python alguns números para comparar. Como você pode ver, ele pode comparar não apenas números, mas também resultados de métodos. Legal, né?

Você deve estar se perguntando por que colocamos dois sinais de igual **==** lado a lado para verificar se os números são iguais. Nós usamos um único **=** para atribuir valores a variáveis. Você sempre, **sempre**, precisa colocar dois **==** se quiser verificar se as coisas são iguais. Também é possível afirmar que as coisas são diferentes. Para isso, usamos o símbolo **!=**, como mostrado no exemplo acima.

Dê ao Python mais duas tarefas:

Já vimos **`>`** e **`<`**, mas o que significam **`>=`** e **`<=`**? Leia da seguinte forma:

- x `>` y significa: x é maior que y
- x `<` y significa: x é menor que y
- x `<=` y significa: x é menor ou igual a y
- x `>=` y significa: x é maior ou igual a y

Fantástico!

- **and** -- se você usar o operador `and`, as duas comparações terão que ser verdadeiras para que a expressão seja verdadeira (True)
- **or** - se você usar o operador `or`, apenas uma das comparações precisa ser verdadeira para que a expressão seja verdadeira (True)

## Booleanos

Aliás, você acabou de aprender sobre um novo tipo de objeto em Python. Ele se chama **booleano**.

Existem apenas dois objetos booleanos:

- **True** (verdadeiro)
- **False** (falso)

Para que o Python entenda, você precisa escrever exatamente **True** (primeira letra maiúscula e as outras minúsculas -- mas sem as aspas). **true, TRUE ou tRUE não vão funcionar -- só True está correto.** (A mesma coisa vale para **False**.)

Booleanos também podem ser variáveis! Veja:

{% filename %}command-line{% endfilename %}

```python
>>> a = True
>>> a
True
```

Parabéns!! :)

Booleanos são um dos recursos mais interessantes na programação, e você acabou de aprender como usá-los!

# Salve!

Até agora, escrevemos todos os códigos no interpretador de Python, que nos limita a digitar uma linha por vez. Programas normais são salvos em arquivos e executados pelo nosso **interpretador** de linguagem de programação ou **compilador**. Até aqui, executamos nossos programas uma linha de cada vez no **interpretador** de Python. Vamos precisar de mais de uma linha de código para as próximas tarefas, então precisaremos rapidamente:

- Sair do interpretador de Python
- Abrir o editor de código de sua escolha
- Salvar algum código em um novo arquivo de Python
- Executar o código!

Para sair do interpretador de Python que estamos usando, simplesmente digite a função `exit()`

{% filename %}command-line{% endfilename %}

```python
>>> exit()
$
```

Isso vai levá-la de volta ao prompt de comando.

Agora, vamos abrir o editor de texto, procure em seu computador o programa `Gedit` (se estiver usando Ubuntu/Linux) e escrever algum código em um novo arquivo:

{% filename %}editor{% endfilename %}

```python
print('Hello, Django girls!')
```

Agora você é uma desenvolvedora Python bastante experiente, então sinta-se livre para escrever códigos com o que aprendeu hoje.

Agora precisamos salvar o arquivo e dar a ele um nome descritivo. Vamos nomear o arquivo **python_intro.py** e salvá-lo na sua área de trabalho. Podemos chamá-lo como quisermos, mas é importante que o nome termine com **.py**. A extensão **.py** diz ao sistema operacional que esse é um **arquivo Python executável** e o interpretador de Python pode rodá-lo.

O arquivo está salvo, então é hora de executá-lo!

<!--sec data-title="Change directory: Windows Command Prompt" data-id="python_windows" data-collapse=true ces-->

No prompt de comando Windows, é assim:

{% filename %}linha de comando{% endfilename %}

    > cd %HomePath%\Desktop


<!--endsec-->

<!--sec data-title="Change directory: Linux Terminal" data-id="python_linux" data-collapse=true ces-->

No prompt de comando Linux, é assim:

{% filename %}linha de comando{% endfilename %}

    $ cd ~/Desktop


<!--endsec-->

Se você tiver alguma dificuldade, é só pedir ajuda. :)

Agora use o interpretador de Python para executar o código que está no arquivo, assim:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hello, Django girls!


Muito bem! Você acabou de rodar seu primeiro programa em Python que foi salvo em um arquivo. Arrasou! ;)

Agora, você pode começar a aprender uma ferramenta essencial na programação:

## If … elif … else

Várias coisas em um código só podem ser executadas se determinadas condições forem atendidas. É por isso que o Python tem um comando chamado **if**.

Substitua o código no arquivo **python_intro.py** pelo seguinte:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
    print('Funciona!')
```

Notou que o texto na linha seguinte ao "if" começa depois de quatro espaços? Chamamos esse tipo de formatação de indentação. Precisamos dessa indentação para que o Python saiba quais linhas executar se a condição dentro do **if** for verdadeira. Você pode usar quantos espaços quiser, mas para que os códigos tenham uma aparência mais limpa e organizada, os programadores de Python costumam usar quatro. Uma tabulação conta como quatro espaços se você configurar seu editor de texto assim. Quando escolher quantos espaços usar, não mude! Se você já começou a indentar com quatro espaços, siga esse padrão em todo o código -- ou você poderá encontrar problemas.

Salve o código e execute outra vez:

{% filename %}command-line{% endfilename %}

```python
$ python3 python_intro.py
Funciona!
```

### E se uma condição não for verdadeira?

Nos exemplos anteriores, o código foi executado somente quando as condições eram verdadeiras. No entanto, o Python também tem as instruções `else` (se não) e `elif` (se não se) :

{% filename %}python_intro.py{% endfilename %}

```python
if 5 > 2:
    print('5 é maior que 2')
else:
    print('5 não é maior que 2')
```

Quando esse código for executado, o Python mostrará:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    5 é maior que 2


Se 2 fosse um número maior que 5, o segundo comando seria executado. Fácil, né? Vamos ver como funciona o `elif`:

{% filename %}python_intro.py{% endfilename %}

```python
nome = 'Maria'
if nome == 'Renata':
    print('Olá Renata!')
elif nome == 'Maria':
    print('Olá Maria!')
else:
    print('Olá estranho!')
```

e executando:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Olá Maria!

Viu o que aconteceu? O `elif` possibilita adicionar uma condição que só vai ser executada se a primeira condição for falsa.

Você pode adicionar quantos `elif` quiser depois do `if`. Por exemplo:

{% filename %}python_intro.py{% endfilename %}

```python
volume = 57
if volume < 20:
    print("Está um pouco baixo")
elif 20 <= volume < 40:
    print("Está bom para música ambiente")
elif 40 <= volume < 60:
    print("Perfeito, posso ouvir todos os detalhes")
elif 60 <= volume < 80:
    print("Ótimo para festas!")
elif 80 <= volume < 100:
    print("Está muito alto!")
else:
    print("Meus ouvidos doem! :(")
```

O Python testa cada condição na sequência em que aparece no código e então mostra:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Perfeito, posso ouvir todos os detalhes


## Comentários

Comentários são linhas que começam com `#`. Você pode escrever o que quiser após o # `` e o Python vai ignorar. Comentários podem tornar seu código mais fácil para outras pessoas entenderem.

Vamos ver como isso funciona:

{% filename %}python_intro.py{% endfilename %}

```python
# Mudar o volume se estiver muito alto ou muito baixo
if volume < 20 or volume > 80
    volume = 50
    print("Bem melhor!")
```

Você não precisa escrever um comentário para cada linha de código, mas eles são úteis para explicar porque o seu código faz alguma coisa ou para fornecer um breve resumo de algo mais complexo.

### Sumário

Nos últimos exercícios você aprendeu:

- a **comparar coisas** -- em Python, você pode comparar objetos usando os operadores `>`, `>=`, `==`, `<=`, `<` e `and`, `or`.
- **Booleano** -- um tipo de objeto que só tem dois valores possíveis: `True` ou `False`.
- a **salvar arquivos** -- armazenar código em arquivos para que você possa executar programas maiores.
- **if... elif... else** -- instruções que permitem que você execute o código somente se determinadas condições forem atendidas.
- **comentários** -- linhas que o Python não executa e que permitem que você documente seu código.

Chegamos à última parte do capítulo!

## Suas próprias funções!

Lembra de funções como `len()`? Boas notícias: agora você vai aprender como escrever suas próprias funções!

Uma função é uma sequência de instruções que o Python deve executar. Cada função em Python começa com a palavra reservada `def` seguida de um nome e, opcionalmente, de uma lista de parâmetros. Vamos fazer uma tentativa. Substitua o código salvo no arquivo **python_intro.py** pelo seguinte:

{% filename %}python_intro.py{% endfilename %}

```python
def oi():
    print('Olá!')
    print('Tudo bem?')

oi()
```

Ok, nossa primeira função está pronta!

Reparou que escrevemos o nome da função no começo e no final do código? O Python lê e executa o código de cima para baixo, então para usar a função que definimos, devemos chamá-la no final. Esclarecendo: no bloco de texto formado pela linha que começa com "def" e as linhas indentadas seguintes, definimos a função, mas não executamos nenhum comando. Precisamos dizer explicitamente ao Python que a execute (escrevendo "oi()").

Vamos executá-la agora e ver o que acontece:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Olá!
    Tudo bem?


> Observação: se não funcionou, não entre em pânico! A saída vai te ajudar a entender o que aconteceu:

- Se você recebeu uma mensagem `NameError`, provavelmente foi um erro de digitação, então confira se você usou o mesmo nome ao criar a função com `def oi()` e quando a chamou no final com `oi()`.
- Se recebeu uma mensagem `IdentationError`, confira se as duas linhas de `print` têm o mesmo recuo no começo: o Python precisa que o código dentro da função esteja bem alinhado.
- Se a função não retornou nenhum resultado, certifique-se de que o útlimo `oi()`*não* esteja indentado - se ele estiver, essa linha vai se tornar parte da função e o Python não vai receber nenhum comando para executar.

Isso foi fácil! Vamos construir nossa primeira função com parâmetros. Usaremos o exemplo anterior - uma função que diz 'oi' para quem o executa - com o nome dessa pessoa:

{% filename %}python_intro.py{% endfilename %}

```python
def oi(nome):
    if nome == 'Maria':
        print('Olá Maria!')
    elif nome == 'Renata':
        print('Olá Renata!')
    else:
        print('Olá estranha!')

oi()
```
Como você pode ver, agora nossa função tem um parâmetro chamado `nome`.

Vamos ver como isso funciona:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

    $ python3 python_intro.py
    Traceback (most recent call last):
    File "python_intro.py", line 10, in <module>
      oi()
    TypeError: oi() missing 1 required positional argument: 'nome'

Oops, um erro. Felizmente, o Python nos fornece uma mensagem de erro bastante útil. Ela diz que a função `oi()` (aquela que definimos) tem um argumento obrigatório (chamado `nome`) e que nós esquecemos de passá-lo ao chamar a função. Vamos resolver isso no final da função:

{% filename %}python_intro.py{% endfilename %}

```python
oi("Maria")
```

E rode novamente:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Olá Maria!

Legal, né? Dessa maneira você não precisa se repetir cada vez que for mudar o nome da pessoa que a função pretende cumprimentar. E é exatamente por isso que precisamos de funções - você não quer precisar repetir seu código!

Parabéns! Você acabou de aprender como criar funções. :)

## Laços

Essa já é a última parte! Rápido, né? :)

Programadores não gostam de repetir código. Programar é automatizar coisas, então não queremos cumprimentar cada pessoa manualmente, certo? É aí que entram os laços (ou "loops", em Inglês).

Ainda se lembra de listas? Vamos fazer uma lista de garotas:

{% filename %}python_intro.py{% endfilename %}

```python
garotas = ['Rachel', 'Monica', 'Phoebe', 'Maria', 'você']
```

A instrução `for` se comporta de maneira similar ao `if`; o código abaixo de qualquer uma destas instrução deve ser indentado com quatro espaços.

Aqui está o código completo que será salvo no arquivo:

{% filename %}python_intro.py{% endfilename %}

```python
def oi(nome):
    print('Oi ' + nome + '!')

garotas = ['Rachel', 'Monica', 'Joana', 'Maria', 'você']
for nome in garotas:
    oi(nome)
```

E quando rodamos:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Oi Rachel!
    Oi Monica!
    Oi Joana!
    Oi Maria!
    Oi você!


Como você pode ver, tudo o que colocar dentro de uma instrução **`for`** com espaço será repetido para cada elemento da lista **`garotas`**.

Você também pode usar o `for` para números usando a função `range`:

{% filename %}python_intro.py{% endfilename %}

```python
for i in range(1, 6):
    print(i)
```

Deve imprimir:

{% filename %}command-line{% endfilename %}

    1
    2
    3
    4
    5


`range` é uma função que cria uma lista de números que se seguem um após o outro (esses números são dados por você como parâmetros).

Note que o segundo desses dois números não está incluído na lista que o Python mostrou (em `range(1, 6)`; ele conta de 1 a 5, mas não inclui o 6). Isso acontece porque o intervalo é semi-aberto, o que significa que ele inclui o primeiro valor, mas não o último.

## Sumário

É isso. **Arrasou!** Esse foi um capítulo difícil, então você deve estar orgulhosa.

Nós estamos orgulhosas de você por ter conseguido ir tão longe!

Para um tutorial de Python oficial e completo, visite https://docs.python.org/3/tutorial/. Lá você encontrará um guia da linguagem mais exaustivo e completo. Até lá :)

Talvez você queira fazer uma breve pausa -- se espreguiçar, andar um pouco, descansar os olhos -- antes de ir para o próximo capítulo. :)

![Cupcake](images/cupcake.png)
