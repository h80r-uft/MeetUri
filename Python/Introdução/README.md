# Introdução

```python
print("Esta é a introdução!")
```

> O programa acima é a exibição mais simples de saída de informações. É uma cópia do código existente no arquivo *"hello.py"*.
>
> Experimente mudar a frase dentro das aspas e executar o código novamente!

## ***Saída de informações***

- `print()`

> É uma função básica de python, que possibilita a exibição de informações para o usuário.

```python
print("Esta é a introdução!")
```

1. Primeiramente chamamos a função através de seu nome `print`
2. Depois disso, usamos **parênteses** para delimitar o que são os argumentos que passaremos.
3. No caso acima passamos apenas um argumento, que é diretamente o texto que queremos exibir.
   - Iremos aprender mais sobre argumentos e passagem de texto posteriormente.

## ***Tipos primitivos***

> Tipos são estruturas básicas que constroem aos poucos seus programas.
>
> São unidades feitas para armazenar informações, e cada uma possui propriedades diferentes.
>
> Python possui quatro destes tipos primitivos, e outros tipos já definidos que você pode estudar mais tarde!

- ***Integers***

  - ```python
    idade = 18
    ```

  - São os **números inteiros**, **positivos** e **negativos**.

  - É possível realizar operações matemáticas com estes.

- ***Floats***

  - ```python
    altura = 1.8
    ```

  - São os números **racionais**.

- ***Booleans***

  - ```python
    esta_chovendo = False
    ```

  - Este tipo representa a informação mais simples, um estado. Pode ser apenas **verdadeira** ou **falsa**.

- ***Strings***

  - ```python
    citacao = "Python é tranquilo"
    ```

  - Com strings podemos armazenar texto, e também realizar operações específicas com este, que você pode estudar posteriormente!

## ***Entrada de informações***

- `input()`

> Outra das funções básicas de python. Esta função irá esperar que o usuário faça a entrada de alguma informação através do console e somente continuará o código depois que o usuário pressionar ***Enter***

```python
input("Escreva seu nome: ")
```

1. Novamente, começamos invocando a função através de seu nome.
2. O argumento de texto que passamos neste caso é opcional, mas indicará ao usuário o que nós queremos que seja feito, e que estamos esperando alguma entrada.

## ***Variáveis***

> Acima não fizemos nenhum uso da informação que o usuário passou, ela apenas se perdeu num código vazio. Vamos dar valor aos dados que foram passados?
>
> Para armazenar estes dados, nos vamos utilizar a função `input` e também declarar variáveis para guardar seus valores.
>
> Uma variável em python é como uma caixa. Ela possui um nome próprio para ser acessada e irá armazenar um valor, que pode ser simples ou muito complexo, como veremos no futuro.

### ***Declaração***

```python
minha_variavel = None
```

1. Nossa variável precisa ter um **nome único**, para que o programa não a confunda com outra variável.
   - Lembre-se de usar nomes que deixem claro qual é o sentido da existência daquela variável. Não precisamos de mais crises existenciais.
2. Usamos o **operador de atribuição** `=` para definir o valor inicial desta.
3. O valor que atribuímos é a palavra-chave `None`. Esta serve para que o programa saiba que aquela variável não possui qualquer valor ainda.

### ***Atribuição***

- Utilizando o operador de atribuição podemos armazenar o valor do resultado de operações ou funções. Por exemplo, podemos guardar o nome de quem utilizar nosso programa e em seguida dar um olá.

```python
nome = input("Digite seu nome: ")
print("Olá", nome)
```

> Tente executar o programa acima e ver como ele funciona!

## ***Conversão de tipos***

> Ao recebermos informações através do console, desejamos trabalhar com estas. Porém em determinadas situações iremos trabalhar com números, e a função `input()` irá interpretar tudo que o usuário escrever como textos.
>
> O que fazer nestes casos?
>
> Nós usamos a conversão de tipos para que a variável receba o valor desejado no tipo que queremos trabalhar.

- `int()`
  - Irá converter uma string ou um número para o tipo inteiro.
- `float()`
  - Converterá uma string ou um número para o tipo de ponto flutuante.
- `str()`
  - Converterá o tipo desejado para sua representação em texto.

> Experimente executar e entender o programa `age.py`.
>
> Modifique-o como desejar!
>
> Ele é uma aplicação prática de tudo que vimos até aqui.