# Lógica

> Anteriormente vimos os operadores lógicos básicos. Vamos começar o módulo de lógica observando a [tabela-verdade](https://pt.wikipedia.org/wiki/Tabela-verdade) destes operadores.

| X     | Y     | X and Y | X or Y | not X |
| ----- | ----- | ------- | ------ | ----- |
| True  | True  | True    | True   | False |
| True  | False | False   | True   | False |
| False | True  | False   | True   | True  |
| False | False | False   | False  | True  |

## `if`

> A keyword `if` é essencial para o desenvolvimento lógico de nossos programas. Sua estrutura básica pode ser vista abaixo.

```python
x = 22
y = 300
if y > x:
    print("y é maior que x")
    print("Isso também está dentro do if")
print("Isso está fora.")
```

> Observando essa estrutura, temos diversos pontos fundamentais.

1. `if`
   - É a palavra chave que identifica este bloco de código.
   - Com ela, o programa estará esperando uma condicional na sequência.
2. `y > x`
   - É a condição. Se verdadeira o código abaixo será executado, do contrário ele será ignorado.
3. `:`
   - Indica o término da condicional e que em sua sequência haverá o código a ser executado.
4. `print()`
   - É o código que queremos executar.
   - Pode ter diversas linhas mas precisamos nos atentar à **indentação**, que são os espaços em branco no começo da linha. São eles que informam ao programa o que está dentro do `if` e o que está fora.

## `else`

> Caso você deseje executar um código apenas para os casos que não cumprirem com a condicional, esta é a palavra-chave para você.

```python
x = 22
y = 300
if y > x:
    print("y é maior que x")
    print("Isso também está dentro do if")
else:
    print("Se você está vendo isso, a condição não foi atendida.")
print("Isso está fora.")
```

> A estrutura deste é bem similar:

1. `else`
   - A *keyword* que identifica este bloco de código
2. `:`
   - Indica que o bloco de código do else está abaixo.
3. `print()`
   - É o código que você deseja executar. Pode ter várias linhas, mas é necessário se atentar à **indentação**.

## `elif`

> O "meio termo" entre as keywords anteriores. Serve para verificar uma nova condição caso a condição anterior não tenha sido atendida.

```python
x = 22
y = 300
if y > x:
    print("y é maior que x")
    print("Isso também está dentro do if")
elif y == x:
    print("y e x são iguais")
else:
    print("Se você está vendo isso, as condições não foram atendidas.")
print("Isso está fora.")
```

> Sua estrutura é muito similar ao `if`

1. `elif`
   - Keyword que identifica este bloco de código.
2. `y == x`
   - Condição utilizada.
3. `:`
   - Simboliza o término da condição e que a sequência será o código a ser executado.
4. `print()`
   - O código que desejamos executar. Pode ser constituído por diversas linhas.
   - Se atente à **indentação**.

## Observações

> Você sempre pode utilizar `if`s dentro de outros `if`s, caso seu programa exija esta complexidade.
>
> Na situação de haver apenas uma linha de código para executar no `if`, ele pode ser reduzido.

```python
if x > y: print("x é maior que y")
```

## Operador ternário

> É uma forma mais curta de implementar `if` e `else`.

```python
x = 33
y = 200

maior = x if x > y else y

print(maior)
```

> O código acima tem o mesmo funcionamento que:

```python
x = 33
y = 200

if x > y:
	maior = x
else:
	maior = y
	
print(maior)
```