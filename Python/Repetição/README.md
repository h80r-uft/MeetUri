# Repetição

> Em determinadas situações podemos desejar que determinado código seja repetido um número específico de vezes, ou enquanto determinada condição for válida.
>
> Para estes casos existem os laços de repetição, que trataremos aqui.

## `while`

> A estrutura `while` é bem simples e direta.
>
> *Enquanto* determinada condição for válida, o código dentro de seu bloco continuará sendo repetido.

```python
presentes = 0
while presentes < 100:
    presentes += 1
    print("Há", presentes, "presentes")
```

A estrutura é similar ao `if`

1. `while`
   - A keyword que identifica esse processo de repetição
2. `presentes < 100`
   - É a condição de execução. Enquanto esta for válida o código irá se repetir.
3. `:`
   - O símbolo que indica o término da condição e início do bloco de código
4. `#codigo`
   - Todo o código que você deseja colocar em repetição. Se atente à **indentação**.

## `for`

> Diferente de algumas outras linguagens de programação, em python o `for` se aproxima mais de um *iterador*, do que de uma estrutura de repetição comum.

- Ele é utilizado para percorrer todos os elementos de uma sequência. *Esta implementação será demonstrada no módulo de listas.*
  - Exemplos de sequência são lista, tupla, dicionário, entre outros.
- Podemos usar esta keyword em conjunto com uma função para aproximar o uso do `for` aqui ao `for` de outras linguagens. *Esta aplicação será vista à seguir.*

## `break`

> Em determinadas circunstâncias podemos desejar o término da repetição antes que a condição se torne falsa. O que fazer nestes casos?
>
> Basta usar a keyword `break`. Ela irá imediatamente interromper o laço, e prosseguir o programa normalmente.

```python
velocidade = 10

while velocidade < 100:
    print("Acelerando...")
    if velocidade == 70:
        break
    velocidade += 10
	
print("Velocidade final:", velocidade)
```

> Execute o código acima para observar seu funcionamento.

## `continue`

> Outra keyword muito útil é a `continue`. Ela faz com que o loop pule a parte do código que estiver abaixo desta no caso da condição se provar verdadeira.
>
> Como exemplo, vamos imaginar que queremos criar um programa capaz de somar os ímpares de 1 à 10, utilizando laços de repetição. O código para tal proeza poderia ser escrito assim:

```python
soma = 0
numero_atual = 0

while numero_atual < 10:
    numero_atual += 1
    if numero_atual % 2 == 0:
        continue
    soma += numero_atual
    
print(soma)
```

## `else`

> Com o uso desta keyword, podemos executar um bloco de código no instante que a condição de um laço de repetição deixar de ser verdadeira.

```python
quacks = 10
while quacks > 0:
    print("QUACK!")
    quacks -= 1
else:
    print("Que silêncio...")
```

> Execute o programa acima para ter uma demonstração de sua funcionalidade.

## `range()`

> A função `range` pode ser utilizada para gerar uma "lista" de números em um intervalo.
>
> Com esta função, podemos usar o `for` para repetir certo código um determinado número de vezes. Vamos observar um exemplo:

```python
for i in range(5):
    print(i)
```

> Executando o programa acima, vemos que ele irá ter a seguinte saída:

```python
0
1
2
3
4
```

> Por que isso acontece? Vamos entender ao observar a estrutura deste `for`:

1. `for`
   - Keyword utilizada para criar esta estrutura de repetição.
2. `i`
   - É o nome da variável que daremos ao valor acessado a cada ciclo da repetição. Poderia ser qualquer outro nome, contanto que não entre em conflito com variáveis já existentes.
3. `in`
   - Esta keyword indica que a variável `i` irá representar os elementos existentes dentro de `range(5)`
4. `range(5)`
   - Uma das aplicações da função. Analisando seu funcionamento, ela recebe entre um e três argumentos, que são:
     1. Valor inicial:
        - Caso não seja declarado, o valor inicial da sequência será 0.
     2. Valor final:
        - É o final do intervalo. Como visto no exemplo acima, é um intervalo aberto, então um `range(5)` acabará em 4.
     3. Incremento:
        - Caso não seja declarado vale 1. É o processo feito após cada ciclo do `for` para que os elementos possam alcançar o valor final. Pode ser negativo, mas não pode ser zero.

> ***Nunca esqueça a indentação adequada e os dois pontos.***

### Como um `for` em ***C*** poderia ser implementado em ***python***?

> Abaixo temos um exemplo simples de `for` em C para imprimir os ímpares de 1 até 10.

```c
#include <stdio.h>
int main()
{
    for (int i = 1; i < 10; i += 2)
    {
        printf("%d\n", i);
    }
}
```

> E aqui podemos comparar com um programa similar, em python.

```python
for i in range(1, 10, 2):
    print(i)
```