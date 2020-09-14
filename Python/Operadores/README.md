# Operadores

> Já sabemos como armazenar dados de diversos tipos, mas eles não seriam tão úteis se não pudéssemos trabalhar seus valores. Aqui iremos aprender alguns dos operadores que temos em Python.

## ***Operadores aritméticos***

> São operações matemáticas realizadas entre variáveis ou valores numéricos diretamente.

| Operador | Descrição                                      | Exemplo      | Contração |
| -------- | ---------------------------------------------- | ------------ | --------- |
| `+`      | Realiza a soma dos elementos                   | `x = x + y`  | `x += y`  |
| `-`      | Realiza a subtração dos elementos              | `x = x - y`  | `x -= y`  |
| `*`      | Realiza a multiplicação dos elementos          | `x = x * y`  | `x *= y`  |
| `/`      | Realiza a divisão dos elementos                | `x = x / y`  | `x /= y`  |
| `%`      | Retorna o resto da divisão entre inteiros      | `x = x % y`  | `x %= y`  |
| `**`     | Retorna o primeiro elemento elevado ao segundo | `x = x ** y` | `x **= y` |
| `//`     | Retorna em inteiro a divisão dos elementos     | `x = x // y` | `x //= y` |

- As contrações são chamadas de ***operadores de atribuição***.

## ***Operadores relacionais***

> Os operadores relacionais comparam dois elementos, e seu retorno é um ***bool***, podendo ser apenas **True** ou **False**, dependendo do resultado da operação efetuada.

| Operador | Nome           | Exemplo  |
| -------- | -------------- | -------- |
| `==`     | Igual          | `x == y` |
| `!=`     | Diferente      | `x != y` |
| `>`      | Maior que      | `x > y`  |
| `<`      | Menor que      | `x < y`  |
| `>=`     | Maior ou igual | `x >= y` |
| `<=`     | Menor ou igual | `x <= y` |

### Exemplo

> Observe o código do programa ***comparison.py***, ele demonstra o uso de alguns operadores relacionais, de conceitos que já vimos anteriormente, e também do operador `%`.
>
> Sinta-se livre para modificar o código. Você pode tentar fazer com que, independente do número escolhido, o usuário ganhe, ou muitas outras modificações

## ***Operadores lógicos***

| Operador | Descrição                                                    | Exemplo                 |
| -------- | ------------------------------------------------------------ | ----------------------- |
| `and`    | Retorna verdadeiro se ambos os elementos forem verdadeiros   | `x < 5 and x < 10`      |
| `or`     | Retorna verdadeiro se ao menos um dos elementos for verdadeiro | `x < 5 or x < 4`        |
| `not`    | Inverte o resultado.                                         | `not(x < 5 and x < 10)` |

## ***Funções matemáticas***

> Python possui diversas operações matemáticas que vão além dos operadores básicos. O uso delas ocorre através de funções, por isso não iremos nos aprofundar muito nas mesmas.
>
> De forma resumida, basta importar a biblioteca de matemática e utilizar a função desejada.

### Exemplo

```python
import math

numero_escolhido = int(input("Insira um número positivo: "))
fatorial = math.factorial(numero_escolhido)
print(fatorial)
```

> Teste o código acima para observar seu funcionamento.
>
> [Aqui está a documentação para mais funções matemáticas desta biblioteca.](https://docs.python.org/3/library/math.html)