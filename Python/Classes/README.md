# Classes

> Python é uma linguagem de programação orientada à objetos. Ela possui um sistema de classes que são moldes desenvolvidos pelo programador para cada objeto individual que ele quiser criar.
>
> Você consegue imaginar os conceitos básicos que definem um notebook, como possuir tela, teclado, ser portátil. Isso é a classe, uma base, um conceito.
> Já os objetos são a aplicação individual dessa base. Da mesma forma que cada modelo de notebook tem especificações diferentes, cada objeto derivado de uma classe tem suas peculiaridades.

## `class`

> A keyword `class` é utilizada para declarar uma nova classe:

```python
class Livro:
    nome = "Python 101"
```

> ***Nunca esqueça a indentação adequada e também os dois pontos!***

## Objetos

> Vamos criar nosso primeiro objeto, tirar essa classe do papel!
>
> Para tal, basta utilizar o construtor da nossa classe. O construtor é uma função que possui o mesmo nome da classe.

```python
class Livro:
    nome = "Python 101"

meu_livro = Livro()
print(meu_livro.nome)
```

> O código acima irá criar um novo objeto da classe Livro, e imprimir o valor do atributo `nome` existente dentro da classe. Iremos nos aprofundar posteriormente, mas para acessar atributos basta utilizar `.nome_do_atributo`
>
> Porém, você poderá observar ao criar mais objetos que todos são iguais. Onde está toda a magia da individualidade dos objetos?
>
> O problema é que nosso construtor não faz nada, então todos os objetos serão criados iguais com o valor padrão dentro da classe.

## `__init__()`

> A função `__init__()` é nosso construtor. Iremos passar diversos parâmetros para que ela defina os atributos de nossos objetos. Lembre-se da declaração de funções, que já estudamos anteriormente.

```python
class Livro:
    def __init__(self, nome, autor):
        self.nome = nome
        self.autor = autor

meu_livro = Livro("Python 101", "Michael Driscoll")

print(meu_livro.nome)
print(meu_livro.autor)
```

> Agora cada objeto terá atributos únicos, baseados na classe, e que dependem do que for passado como argumento.
>
> Você pode ter percebido algo estranho na função `__init__()`. Estamos declarando 3 argumentos, `self, nome, autor`, mas na hora de usar o construtor passamos apenas dois argumentos. Por quê?

## `self`

> O `self` na função `__init__()` é especial. Ele representa uma referência ao objeto que está executando aquele código, e **precisa ser o primeiro argumento**. O nome pode ser alterado como desejar.
>
> Vamos observar isso no código abaixo.

```python
class Livro:
    def __init__(meu_objeto, nome, autor):
        meu_objeto.nome = nome
        meu_objeto.autor = autor
        
    def minha_funcao(exemplo):
        print(exemplo.nome)
        print(exemplo.autor)

meu_livro = Livro("Python 101", "Michael Driscoll")

meu_livro.minha_funcao()
```

## Funções de objetos

> Acima vimos outra propriedade muito interessante dos objetos, eles possuem métodos próprios.
>
> A estrutura é bem simples, é uma declaração de função normal, mas o primeiro argumento vai ser a referência ao próprio objeto.

```python
class Livro:
    def __init__(self, nome, autor):
        self.nome = nome
        self.autor = autor
        
    def minha_funcao(self):
        print(self.nome)
        print(self.autor)

meu_livro = Livro("Python 101", "Michael Driscoll")

meu_livro.minha_funcao()
```

## Acessando propriedades de objetos

> Já vimos anteriormente como acessar as propriedades de um objeto, mas isso também é válido para modificar seus valores:

```python
class Livro:
    def __init__(self, nome, autor):
        self.nome = nome
        self.autor = autor
        
    def minha_funcao(self):
        print(self.nome)
        print(self.autor)

meu_livro = Livro("Python 101", "Michael Driscoll")

meu_livro.minha_funcao()

meu_livro.nome = "Mudei"
meu_livro.autor = "Mudou também"

meu_livro.minha_funcao()
```

## Funções estáticas

> Pode ser interessante criar funções em suas classes que não dependem de um objeto único. Para tal existem as funções estáticas. São funções chamadas utilizando o nome da classe, em vez de um objeto, e o primeiro argumento, caso exista, não é necessariamente a referência à um objeto desta classe.

```python
class Livro:
    def __init__(self, nome, autor):
        self.nome = nome
        self.autor = autor
        
    def minha_funcao(self):
        print(self.nome)
        print(self.autor)
        
    @staticmethod
    def funcao(texto):
        return "A função dos livros é %s." % texto
    
print(Livro.funcao("transmitir informação"))
```

- Se atente ao `@staticmethod`, ele é um ***decorador*** que transforma a função abaixo em uma função estática, independente de uma instância de objeto.