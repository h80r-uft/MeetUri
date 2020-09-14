# Aprofundando os básicos

## `input()`

> `input()`  é uma função que lê e retorna o texto inserido pelo usuário, encerrando sua leitura na quebra de linha. Em determinadas situações, podemos querer receber diversas entradas diferentes em uma linha só. Vamos ver o exemplo à seguir:

```markdown
# Enunciado
> Seu trabalho é receber um número inicial, que indica o tamanho de uma sequência, e posteriormente uma sequência de números. Após receber estes valores, imprimir o dobro de cada valor, um valor por linha.

# Exemplo de Entrada
5
2 5 4 20 10

# Exemplo de Saída
4
10
8
40
20

```

> Como poderíamos atender esse pedido?
>
> Vejamos o exemplo de solução abaixo:

```python
quantidade = int(input())
valores = input().split()

for i in range(quantidade):
    valores[i] = int(valores[i])

for num in valores:
    print(2 * num)
```

> Neste caso, utilizamos o método das [strings](https://docs.python.org/3/library/stdtypes.html#string-methods) chamado `split()`. O que ele faz é transformar uma string única em uma lista de strings, utilizando os espaços em branco como separador de elementos.
>
> Como a variável valores se torna uma lista de **strings** e precisamos fazer uma operação **aritmética** com seus elementos, é necessário converter estes para **inteiros**. É isso que está sendo feito no primeiro `for`.
>
> Com um código um pouco mais avançado, é possível encurtar esse programa:

```python
quantidade = int(input())
valores = list(map(int, input().split()))

for num in valores:
    print(2 * num)
```

> O método `map()` recebe dois parâmetros, o primeiro é a ***função*** que será utilizada para converter os valores da lista. No nosso caso é a função `int()`. Mas como ele deseja receber a função, e não executar ela no argumento, passamos sem os parênteses.
>
> O segundo é a coleção que será convertida.
>
> Como este método retorna um **mapa**, precisamos converter para **lista**, usando a função `list()`.

## Atribuição

### Atribuição Múltipla

> Podemos inicializar várias variáveis simultaneamente usando vírgulas para separar a variável e seu respectivo valor.

```python
x = 1
y = 2
```

> Usando a atribuição múltipla, poderíamos atribuir:

```python
x, y = 1, 2
```

## `print()`

> Vimos anteriormente uma forma simples de imprimir texto estático e variável, que era passando diferentes argumentos com vírgula para a função `print()`. Em python também podemos realizar uma formatação similar ao estilo de formatação de `printf`:

```python
nome = "Anna"
idade = 18

print("A", nome, "possui", idade, "anos")
```

> No exemplo acima observamos com facilidade como pode se tornar complexo conforme o número de variáveis aumenta.
>
> Vamos melhorar esse programa:

```python
nome = "Anna"
idade = 18

print("A %s possui %d anos" % (nome, idade))
```

> Pronto, o texto está mais legível, e de forma geral mais fácil de compreender.
> Agora o que são esses símbolos `%s` e `%d`?
>
> Vamos nos atentar à estrutura:

- `print(formato % (valores))`
  - `%s` indica que lá irá a primeira variável da lista de valores, e que ela é uma **s**tring.
  - `%d` indica o local da segunda variável, e que esta é um inteiro.
  - `%` representa o operador de módulo. Para strings ele funciona de forma especial. Ele irá inserir os valores que estão à direita no padrão de formatação à esquerda. E para tal, é necessário utilizar caracteres especiais na formatação, que indiquem onde irão os valores. Estes são os `%s` e `%d`
  - `(valores)` é uma lista com todas as variáveis que serão utilizadas, na ordem correta.

> Temos uma tabela especial para a [formatação de strings](https://docs.python.org/3/library/stdtypes.html#printf-style-string-formatting), você deve utilizar um ***%*** e em seguida uma das letras à seguir:

| Conversão | Significado                                   |
| --------- | --------------------------------------------- |
| ***d***   | Número inteiro                                |
| ***i***   | Número inteiro                                |
| ***f***   | Número de ponto flutuante                     |
| ***s***   | String                                        |
| ***%***   | Te permite utilizar o "%" como texto simples. |

> *Lembrando que estes são apenas alguns dos itens da tabela.*

## End Of File - `EOF`

> Algumas vezes poderemos trabalhar com arquivos para realizar a entrada de valores. Isso ocorre no URI. Nestas situações precisamos fazer a leitura até atingir o *fim do arquivo*, este é o chamado **End Of File**, ou ***EOF***.
>
> O URI pode se referir à estes eventos simplesmente com textos como *"a entrada contém vários casos de teste"*, então se atente ao exemplo de entrada, e se não houver uma condição de término você já sabe, é ***EOF***!

```python
while True:
    try:
        # Seu código aqui
    except EOFError:
        break
```

> `while True:` inicia um laço de repetição teoricamente infinito, já que a condição de parada não é declarada no `while`. No nosso caso, ele vai parar quando ocorrer o erro que indica fim de arquivo.
>
> `try` e `except` são keywords utilizadas para o tratamento de erros. Como são mais avançadas elas não foram tratadas aqui, mas sinta-se livre para pesquisar mais.
>
> O importante está em se atentar à grafia de `EOFError` este erro específico indica que o arquivo de entrada chegou ao final e seu programa será encerrado.
>
> Agora você pode enfrentar o ***EOF*** sem medo de errar!