# Miniguia de Estudo — Estruturas de Dados e Funções em Python

Este miniguia reúne os principais conceitos estudados sobre **listas, tuplas, conjuntos, dicionários e funções em Python**, com base nos materiais utilizados como fontes no NotebookLM.

---

## 1. Listas

As listas permitem armazenar vários objetos de forma sequencial. Elas podem conter diferentes tipos de dados e são **mutáveis**, ou seja, seus valores podem ser modificados depois da criação.

### Criando uma lista

```python
frutas = ["laranja", "maçã", "uva"]
numeros = list(range(10))
```

### Acessando elementos

Os elementos podem ser acessados utilizando índices, começando pela posição `0`.

```python
frutas = ["maçã", "laranja", "uva", "pera"]

print(frutas[0])  # maçã
print(frutas[2])  # uva
```

Também é possível utilizar índices negativos:

```python
print(frutas[-1])  # pera
```

### Fatiamento

O fatiamento permite acessar partes de uma lista.

```python
lista = ["p", "y", "t", "h", "o", "n"]

print(lista[2:])
print(lista[:2])
print(lista[1:3])
```

### Alguns métodos importantes

```python
lista.append("Python")
lista.remove("Python")
lista.clear()
lista.copy()
lista.count("Python")
lista.reverse()
lista.sort()
```

### Quando utilizar?

Listas são úteis quando precisamos armazenar vários elementos e queremos poder adicionar, remover ou modificar esses valores durante a execução do programa.

---

## 2. Tuplas

As tuplas são estruturas parecidas com listas, porém sua principal diferença é que são **imutáveis**. Depois de criadas, seus elementos não podem ser alterados diretamente.

### Criando uma tupla

```python
frutas = ("laranja", "pera", "uva")
numeros = tuple([1, 2, 3, 4])
```

### Acessando elementos

Assim como listas, as tuplas utilizam índices.

```python
frutas = ("maçã", "laranja", "uva", "pera")

print(frutas[0])
print(frutas[2])
print(frutas[-1])
```

### Fatiamento

```python
tupla = ("p", "y", "t", "h", "o", "n")

print(tupla[2:])
print(tupla[:2])
print(tupla[::-1])
```

### Métodos apresentados

```python
tupla.count("valor")
tupla.index("valor")
len(tupla)
```

### Quando utilizar?

Tuplas são úteis quando queremos trabalhar com uma sequência de valores que não deve ser modificada durante a execução do programa.

---

## 3. Conjuntos

Os conjuntos, representados pelo tipo `set`, armazenam elementos sem repetição. Eles podem ser usados para representar conjuntos matemáticos ou eliminar itens duplicados.

### Criando um conjunto

```python
numeros = {1, 2, 3, 4}
```

Também podemos criar um conjunto usando `set()`:

```python
numeros = set([1, 2, 3, 1, 3, 4])

print(numeros)
# {1, 2, 3, 4}
```

### Atenção

Conjuntos não suportam indexação nem fatiamento.

Portanto, não fazemos:

```python
numeros[0]
```

### União

```python
conjunto_a = {1, 2}
conjunto_b = {3, 4}

print(conjunto_a.union(conjunto_b))
```

Resultado:

```text
{1, 2, 3, 4}
```

### Interseção

```python
conjunto_a = {1, 2, 3}
conjunto_b = {2, 3, 4}

print(conjunto_a.intersection(conjunto_b))
```

Resultado:

```text
{2, 3}
```

### Diferença

```python
print(conjunto_a.difference(conjunto_b))
```

Resultado:

```text
{1}
```

### Outros métodos

```python
conjunto.add(valor)
conjunto.remove(valor)
conjunto.discard(valor)
conjunto.clear()
conjunto.copy()
```

### Quando utilizar?

Conjuntos são úteis principalmente quando queremos:

* eliminar valores repetidos;
* comparar grupos de elementos;
* realizar operações como união, interseção e diferença.

---

## 4. Dicionários

Os dicionários armazenam informações utilizando pares de **chave e valor**. Cada chave é utilizada para identificar um determinado valor.

### Criando um dicionário

```python
pessoa = {
    "nome": "Guilherme",
    "idade": 28
}
```

Também podemos utilizar:

```python
pessoa = dict(nome="Guilherme", idade=28)
```

### Acessando valores

Os dados são acessados através das chaves.

```python
dados = {
    "nome": "Guilherme",
    "idade": 28
}

print(dados["nome"])
print(dados["idade"])
```

### Modificando valores

```python
dados["nome"] = "Maria"
dados["idade"] = 18
```

### Adicionando um novo valor

```python
dados["telefone"] = "9999-9999"
```

### Percorrendo um dicionário

```python
for chave, valor in dados.items():
    print(chave, valor)
```

### Alguns métodos importantes

```python
dados.get("nome")
dados.keys()
dados.items()
dados.pop("nome")
dados.clear()
dados.copy()
```

### Quando utilizar?

Dicionários são úteis quando precisamos relacionar uma informação a um identificador.

Por exemplo:

```python
aluno = {
    "nome": "Ana",
    "idade": 20,
    "curso": "Python"
}
```

Nesse caso, `"nome"`, `"idade"` e `"curso"` são as chaves.

---

## 5. Funções

Uma função é um bloco de código identificado por um nome. Ela pode receber parâmetros e ajuda a tornar o código mais legível e reutilizável.

### Criando uma função

```python
def exibir_mensagem():
    print("Olá mundo!")
```

Executando:

```python
exibir_mensagem()
```

### Função com parâmetro

```python
def exibir_mensagem(nome):
    print(f"Seja bem-vindo {nome}!")

exibir_mensagem("Maria")
```

### Parâmetro com valor padrão

```python
def exibir_mensagem(nome="Anônimo"):
    print(f"Seja bem-vindo {nome}!")
```

### Retornando valores

Para retornar um resultado, utilizamos a palavra-chave `return`. O material também destaca que uma função Python retorna `None` por padrão quando nenhum valor é retornado explicitamente.

```python
def calcular_total(numeros):
    return sum(numeros)

resultado = calcular_total([10, 20, 34])

print(resultado)
```

### Argumentos nomeados

Também podemos passar argumentos utilizando `nome=valor`.

```python
def salvar_carro(marca, modelo, ano):
    print(marca, modelo, ano)

salvar_carro(
    marca="Fiat",
    modelo="Palio",
    ano=1999
)
```

### `*args` e `**kwargs`

O material também apresenta `*args` e `**kwargs`. Nesses casos, os valores recebidos ficam disponíveis como tupla e dicionário, respectivamente.

### Quando utilizar funções?

Funções são úteis para:

* evitar repetição de código;
* dividir um programa em partes menores;
* organizar melhor a lógica;
* reaproveitar uma mesma operação diversas vezes.

---

# Comparação rápida

| Estrutura  | Principal característica              |
| ---------- | ------------------------------------- |
| Lista      | Sequência mutável                     |
| Tupla      | Sequência imutável                    |
| Conjunto   | Não possui elementos repetidos        |
| Dicionário | Organiza informações em chave e valor |
| Função     | Agrupa e reutiliza blocos de código   |

---

# Glossário

### Mutável

Objeto que pode ser alterado depois de sua criação.

### Imutável

Objeto que não pode ser alterado depois de criado.

### Índice

Posição utilizada para acessar um elemento de uma sequência.

### Chave

Identificador utilizado para acessar um valor dentro de um dicionário.

### Valor

Informação associada a uma chave.

### Parâmetro

Informação definida na declaração de uma função para receber valores.

### Argumento

Valor fornecido para uma função quando ela é chamada.

### `return`

Palavra-chave utilizada para retornar um valor de uma função.

### `set`

Tipo utilizado para representar conjuntos em Python.

---

# Prompts para revisão

## Revisão de um conceito

```text
Explique [CONCEITO] em Python de forma simples.

Apresente:
- definição;
- sintaxe;
- exemplo;
- principais operações;
- um erro comum.
```

## Comparação

```text
Compare [CONCEITO A] e [CONCEITO B] em Python.

Explique as principais diferenças e dê um exemplo
de quando utilizar cada um.
```

## Exercícios

```text
Crie três exercícios sobre [CONCEITO] em Python.

Comece com um exercício fácil e aumente a dificuldade.

Não mostre as respostas imediatamente.
```

## Quiz

```text
Faça um quiz sobre [CONCEITO].

Faça uma pergunta por vez e espere minha resposta
antes de mostrar a explicação.
```

## Análise de código

```text
Analise o código abaixo e explique quais conceitos
de Python estão sendo utilizados.

Explique linha por linha.

[CÓDIGO]
```

---

# Conclusão

O estudo dessas estruturas permite compreender diferentes formas de organizar e manipular dados em Python.

Listas e tuplas trabalham com sequências de elementos, conjuntos são úteis para trabalhar com valores únicos, dicionários organizam informações por meio de chaves e valores e funções permitem organizar e reutilizar partes do código.

Dominar esses conceitos fornece uma base importante para avançar no desenvolvimento de programas mais completos utilizando Python.
