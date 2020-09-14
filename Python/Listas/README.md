# Listas

> Python possui quatro tipos de coleções de dados:

- ***Lista***
  - Uma coleção ordenada e modificável.
  - Permite membros duplicados.
- ***Tupla***
  - Uma coleção ordenada e imutável.
  - Permite membros duplicados.
- ***Set***
  - Uma coleção sem ordem estática e sem índices.
  - Não permite membros duplicados.
- ***Dicionário***
  - Uma coleção sem ordem estática, mas modificável e indexada.
  - Não permite índices.

> Ao usar coleções, é importante ter conhecimento das limitações e do funcionamento de cada uma para escolher a que melhor se adeque à necessidade.
>
> Vamos expor aqui apenas as Listas, mas sinta-se livre para estudar as outras coleções.

## Criando listas

> Em python a criação de listas se dá pelo uso de colchetes:

```python
frutas = ["maçã", "banana", "morango"]
print(frutas)
```

> Usando o código acima, iremos ter uma única variável `frutas` armazenando *três strings diferentes*, como pode ser visto ao imprimir a própria variável.

## Acessando itens

> Agora, se fossemos parar nisso não seria muito útil, porque bastaria fazer uma string normal, contendo os três elementos.
>
> Então vamos acessar cada item individualmente.
>
> Para isso basta utilizar novamente os colchetes, mas desta vez ao lado da variável já criada:

```python
frutas = ["maçã", "banana", "morango"]
print(frutas[1])
```

> Agora vemos que apenas o segundo elemento foi exibido.
>
> Sim, o **segundo** elemento foi exibido ao utilizarmos `1` dentro dos colchetes. Por quê?
>
> Ao colocarmos colchetes ao lado de uma lista, estamos acessando um índice específico dentro desta. Precisamos nos lembrar que python utiliza uma [**indexação de base 0**](https://en.wikipedia.org/wiki/Zero-based_numbering). Portanto, o primeiro elemento da lista possuirá índice 0, o segundo será 1, e assim sucessivamente.

### Indexação negativa

> Em python também podemos usar índices negativos, e estes irão do final ao início da lista.

```python
frutas = ["maçã", "banana", "morango"]
print(frutas[-1])
```

> No exemplo acima, o elemento acessado será o último elemento. `-2` representaria o penúltimo, `-3` o antepenúltimo...

### Intervalo de índices

> Também podemos descrever um intervalo de índices, e desta forma receber uma nova lista contendo apenas os elementos dentro do intervalo.

```python
frutas = ["maçã", "banana", "morango", "laranja", "abacaxi", "melancia", "manga"]
print(frutas[2:5])
```

> A sintaxe neste caso é:

- `variavel[indice_inicial:indice_final]`
  - Lembrando que isso gera um intervalo de **início fechado e final aberto**, portanto no exemplo acima o elemento de índice 5 não será incluído.

> Este processo de obter o intervalo de índices em python é chamado de *[slicing](https://stackoverflow.com/questions/509211/understanding-slice-notation)*, e pode ser uma ferramenta muito útil.

## Modificando itens

> Para modificar é muito simples. Basta acessar o elemento que se deseja modificar, e utilizar um operador de atribuição com este.

```python
frutas = ["maçã", "banana", "morango"]
frutas[1] = "uva"
print(frutas)
```

## Iterando sobre a lista

> Para acessar todos os valores da lista, um de cada vez, podemos usar o `for`, que já conhecemos anteriormente.

```python
frutas = ["maçã", "banana", "morango"]
for fruta in frutas:
	print(fruta)
```

> Aqui observamos a seguinte sintaxe:

- `for variavel in lista:`
  - `variavel` é o nome pelo qual chamaremos cada elemento individual da lista. Contanto que não entre em conflito com variáveis já existentes, pode ser qualquer nome.
  - `lista` é a lista de elementos que queremos analisar.

> **Não se esqueça dos dois pontos e de indentar corretamente!**

### Observação

> Utilizar operadores de atribuição na `variavel` não irá modificar o valor do elemento dentro da lista.

## Verificando valores

> Você quer saber se determinado elemento existe dentro de uma lista? Podemos combinar algumas das keywords já conhecidas para obter esse resultado.

```python
frutas = ["maçã", "banana", "morango"]
if "morango" in frutas:
	print("Temos morango!")
```

> **Novamente, não se esqueça dos dois pontos e da indentação adequada.**

- `if elemento in lista:`
  - O `elemento` é o que desejamos encontrar. Ele irá comparar este elemento com todos os elementos da lista e, caso encontre, executar o código em seu bloco.

## Comprimento da lista

> Pode ser muito útil saber quantos itens existem dentro de uma lista. Mas como vamos obter essa informação?
>
> Podemos usar um `for` e uma variável para incrementar ao passar pelos itens da lista.

```python
frutas = ["maçã", "banana", "morango"]
comprimento = 0
for elemento in frutas:
	comprimento += 1
print(comprimento)
```

> O código acima funciona bem, mas e se houvesse um jeito de fazer isso com bem menos esforço?
>
> Em python há! Basta usarmos a função `len()`. Ela recebe como parâmetro uma coleção e irá retornar o comprimento da mesma.

```python
frutas = ["maçã", "banana", "morango"]
print(len(frutas))
```

## Adicionando itens

> Listas são conjuntos modificáveis, então podemos adicionar novos elementos à elas também. Para adicionar, iremos utilizar métodos existentes dentro das listas. Estes métodos são tipos de funções que são específicos de um objeto. São termos confusos mas que explicaremos melhor posteriormente.
>
> Por enquanto basta memorizar a sintaxe de uso destes.
>
> Temos dois métodos de adição:

### `append()`

> Este método irá **adicionar o novo elemento *ao fim da lista*.**

```python
frutas = ["maçã", "banana", "morango"]
frutas.append("melancia")
print(frutas)
```

> A sintaxe para uso de métodos de listas é:

- `lista.metodo()`
  - `lista` representa a variável que é a lista trabalhada.
  - `.` indica que estamos acessando algo dentro do objeto, neste caso um método.
  - `metodo` representa o nome do método desejado.
  - `()` indica que queremos executar o método. Sem os parênteses o programa iria acreditar que só queremos ver o método, e não executá-lo.

### `insert()`

> Este método **adicionará o elemento *no índice desejado***.

```python
frutas = ["maçã", "banana", "morango"]
frutas.insert(1, "melancia")
print(frutas)
```

## Removendo itens

> Há diversas formas de se remover um item.

### `remove()`

> Este método recebe um elemento, e irá remover o elemento da lista, caso presente.

```python
frutas = ["maçã", "banana", "morango"]
frutas.remove("banana")
print(frutas)
```

### `pop()`

> Este método pode receber um argumento, o índice, e irá remover o elemento desejado, também retornando seu valor.
>
> Caso não seja passado um índice, ele irá remover o último elemento.
>
> Esta função é especialmente útil se você deseja ter acesso ao elemento, e simultaneamente remover o mesmo da lista.

```python
frutas = ["maçã", "banana", "morango"]
removido = frutas.pop()
print(removido)
print(frutas)
```

### `del`

> A keyword `del` irá apagar o elemento que você indicar. Também pode ser usada para apagar a lista completa.

```python
frutas = ["maçã", "banana", "morango"]
del frutas[1]
print(frutas)
```

### `clear()`

> Também é possível esvaziar a lista, e este é o método específico para isso.

```python
frutas = ["maçã", "banana", "morango"]
frutas.clear()
print(frutas)
```

## Copiando listas

> Podemos desejar criar cópias das listas que usarmos. Mas apenas usar operadores de atribuição para isso, fazendo por exemplo `lista2 = lista1` não funcionará.
>
> Isso ocorre porque a `lista2`, no exemplo acima, passaria a ser uma referência aos elementos da `lista1`. Assim qualquer mudança na `lista1` afetaria também a outra lista.

### `copy()`

> O método `copy()` cria uma cópia da lista original, que pode ser modificada sem interferência.

```python
frutas = ["maçã", "banana", "morango"]
copia = frutas.copy()
copia[0] = "uva"
print(frutas)
print(copia)
```

### `list()`

> O construtor de listas `list()` pode receber como argumento uma lista, e irá criar uma cópia da lista passada.

```python
frutas = ["maçã", "banana", "morango"]
copia = list(frutas)
copia[0] = "uva"
print(frutas)
print(copia)
```

## Unindo listas

> Temos diversas maneiras de unir duas listas diferentes.

### `+`

> É a forma mais simples de concatenar as listas.

```python
frutas = ["maçã", "banana", "morango"]
verduras = ["couve-flor", "alface", "brócolis"]

cesta = frutas + verduras

print(cesta)
```

### `append()`

> Podemos usar a união de um `for` com o `append()` para acrescentar um à um os elementos de uma lista na outra.

```python
frutas = ["maçã", "banana", "morango"]
verduras = ["couve-flor", "alface", "brócolis"]

cesta = frutas.copy()
for elemento in verduras:
	cesta.append(elemento)
	
print(cesta)
```

### `extend()`

> O método `extend()` tem como função acrescentar todos os elementos de uma lista no final de outra, facilitando um pouco o trabalho.

```python
frutas = ["maçã", "banana", "morango"]
verduras = ["couve-flor", "alface", "brócolis"]

cesta = frutas.copy()
cesta.extend(verduras)
	
print(cesta)
```

## `list()`

> O construtor da classe ***list***. ele pode receber qualquer coleção como argumento e irá criar uma lista baseada nisso.
>
> Também é possível usar esta função sem argumentos, criando uma lista vazia.
>
> E, com a sintaxe abaixo, podemos criar uma lista usando este construtor.

```python
frutas = list(("maçã", "banana", "morango"))
```

- Não se esqueça dos **parênteses duplos**.

> O que ocorre acima na verdade é a criação de uma ***tupla***, que é convertida para lista. Por isso há a necessidade de parênteses duplos. O par mais interno é responsável pela criação da tupla, e o mais externo são os parênteses da função construtora.

## Métodos de listas

> Python possui [diversos métodos nativos nas listas](https://docs.python.org/3/library/stdtypes.html#list), aqui teremos um resumo deles.

| Método      | Descrição                                                    |
| ----------- | ------------------------------------------------------------ |
| `append()`  | Adiciona um elemento ao fim da lista.                        |
| `clear()`   | Remove todos os elementos da lista.                          |
| `copy()`    | Retorna uma cópia da lista.                                  |
| `count()`   | Retorna quantas vezes o elemento especificado se repete na lista. |
| `extend()`  | Adiciona os elementos da coleção especificada para o fim da lista atual. |
| `index()`   | Retorna o índice da primeira ocorrência do elemento especificado. |
| `insert()`  | Adiciona um elemento em uma posição especificada.            |
| `pop()`     | Remove o elemento de uma posição especificada e retorna seu valor. |
| `remove()`  | Remove o elemento especificado.                              |
| `reverse()` | Inverte a ordem da lista.                                    |
| `sort()`    | Ordena a lista.                                              |

