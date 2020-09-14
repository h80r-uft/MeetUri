# Funções

> Já vimos diversas funções que existem em python, mas vamos fazer algo mais legal agora: Criar nossas próprias funções!

- Por que criar funções?
  - Evitar a repetição de código
  - Melhor organizar seu programa
  - Testar etapas exclusivas de um processo maior com facilidade
  - Estender a aplicação de um método para algo além do que foi originalmente imaginado.

## Criação

> Para criar nossas funções, utilizamos a keyword `def`:

```python
def minha_funcao():
    print("Oi")
```

> No código acima podemos observar a seguinte estrutura:

- `def nome():`
  - `def` é a keyword utilizada para declarar a função.
  - `nome` é o nome único de sua função.
  - `()` nos parênteses passaremos o nome dos parâmetros exigidos. Neste caso, a função não requer parâmetros.

> ***Não se esqueça da indentação e dos dois pontos!***

## Chamada

> Para executar sua função, basta utilizar seu nome, e não se esquecer dos parênteses. Exatamente como já estávamos fazendo antes!

```python
def minha_funcao(nome):
    print("oi %s" % nome)
    
minha_funcao(input())
```

## Argumentos

> Como vimos acima, basta colocar o nome do argumento que desejamos que a função tenha, e passar o mesmo na hora da chamada.
>
> Quando criamos a função, declaramos uma quantidade de argumentos. Ao chamar esta função, precisamos passar a quantidade certa de parâmetros, ou receberemos um erro.
>
> Existem tipos diferentes de argumentos, que veremos agora:

### Argumentos arbitrários

> Existem funções que recebem um número variável de argumentos. Para tal podemos usar os argumentos arbitrários. Estes se tornam uma tupla com todos os valores passados na chamada da função.
>
> Para tornar um argumento arbitrário, basta adicionar um `*` antes do nome do argumento.

```python
def minha_funcao(*pessoas):
    print("A pessoa mais velha é %s" % pessoas[-1])

minha_funcao(input(), input(), input())
```

### Keyword Arguments

> Quando utilizamos vários argumentos, desconsiderando argumentos arbitrários, a ordem é essencial.
>
> Caso você deseje, podemos nomear os argumentos na chamada da função, para assim ignorar a ordem.

```python
def minha_funcao(fruta1, fruta2, fruta3):
    print("A fruta mais gostosa é", fruta1)
    
minha_funcao(fruta3 = "uva", fruta1 = "melancia", fruta2 = "laranja")
```

### Arbitrary Keyword Arguments

> Podemos passar argumentos arbitrários no formato de chave-valor, colocando mais uma `*` antes do nome da variável arbitrária.
>
> Estude a estrutura de [dicionário](https://docs.python.org/3/tutorial/datastructures.html#dictionaries) para entender melhor esta aplicação caso surjam dúvidas.

```python
def minha_funcao(**pessoa):
    print("%s, %d anos." % (pessoa["nome"], pessoa["idade"]))
    
minha_funcao(idade = 18, nome = "João")
```

### Valor padrão de argumentos

> Também é possível definir um valor padrão para determinado argumento, desta forma caso ele não seja passado, terá um valor base. Desta forma é possível ter argumentos opcionais.

```python
def minha_funcao(clima = "quente"):
    print("Hoje está " + clima)
    
minha_funcao("tranquilo")
minha_funcao()
```

## Retornar valores

> Já vimos algumas funções que retornam alguma informação, como a função `input()`. Para que nossas funções também possuam algum retorno é bem simples! Basta utilizar a keyword `return`.

```python
def dobro(x):
    return x * 2

print(dobro(4))
print(dobro(8))
```

## Recursividade

> É uma forma de repetir o processo da função até que ela alcance uma condição especificada por você. Para tal, basta chamar a função no próprio código da função, e garantir que ela possui alguma forma de parar esse novo "loop".

```python
def recursividade(x):
    if x == 8:
        return ""
    if x > 8:
        return " + 1" + recursividade(x - 1)
    else:
        return " - 1" + recursividade(x + 1)

def oito(x):
  return "8" + recursividade(x) + " = " + str(x)

print(oito(16))
print(oito(4))
```