# Sistemas operacionais - Introdução às Threads em Python (2024.2)

## Informações gerais
- **Público alvo**: alunos da disciplina de SO (Sistemas Operacionais) do curso de TADS (Superior em Tecnologia em Análise e Desenvolvimento de Sistemas) no CNAT-IFRN (Instituto Federal de Educação, Ciência e Tecnologia do Rio Grande do Norte - Campus Natal-Central).
- disciplina: **SO** Sistemas Operacionais
- professor: [Leonardo A. Minora](https://github.com/leonardo-minora)
- texto gerado pelo [Microsoft Copilot](https://copilot.microsoft.com/)

## Conceito inicial

**Threads** são unidades de execução dentro de um processo. Elas permitem que um programa realize múltiplas operações simultaneamente, o que pode melhorar a eficiência e o desempenho, especialmente em tarefas que envolvem I/O ou operações que podem ser paralelizadas.

## Código-fonte 1 : Gerando os números aleatórios
### Código Completo : Gerando os números aleatórios

Aqui está o código completo para referência:

```python
import random

# Gerar uma lista de 1000 números aleatórios
numeros = [random.randint(1, 100) for _ in range(1000)]

# Exportar a lista para um arquivo texto
with open('numeros_aleatorios.txt', 'w') as arquivo:
    for numero in numeros:
        arquivo.write(f"{numero}\n")

print("A lista de 1000 números aleatórios foi exportada para o arquivo 'numeros_aleatorios.txt'.")
```

### Passo 1: Importar o Módulo `random`

Primeiro, precisamos importar o módulo `random`, que contém funções para gerar números aleatórios.

```python
import random
```

### Passo 2: Gerar a Lista de Números Aleatórios

Usamos uma list comprehension para gerar uma lista de 1000 números aleatórios entre 1 e 100. A função `random.randint(a, b)` retorna um número inteiro aleatório `N` tal que `a <= N <= b`.

```python
numeros = [random.randint(1, 100) for _ in range(1000)]
```

Aqui, `random.randint(1, 100)` gera um número aleatório entre 1 e 100, e o loop `for _ in range(1000)` repete isso 1000 vezes para criar a lista.

### Passo 3: Exportar a Lista para um Arquivo Texto

Abrimos um arquivo texto em modo de escrita (`'w'`) usando a função `open()`. Em seguida, escrevemos cada número da lista no arquivo, cada um em uma nova linha.

```python
with open('numeros_aleatorios.txt', 'w') as arquivo:
    for numero in numeros:
        arquivo.write(f"{numero}\n")
```

- `with open('numeros_aleatorios.txt', 'w') as arquivo:` abre o arquivo `numeros_aleatorios.txt` para escrita. O uso do `with` garante que o arquivo será fechado corretamente após a escrita.
- `for numero in numeros:` itera sobre cada número na lista `numeros`.
- `arquivo.write(f"{numero}\n")` escreve o número no arquivo seguido por uma nova linha (`\n`).

### Passo 4: Mensagem de Confirmação

Por fim, imprimimos uma mensagem de confirmação para informar que a lista foi exportada com sucesso.

```python
print("A lista de 1000 números aleatórios foi exportada para o arquivo 'numeros_aleatorios.txt'.")
```


## Código fonte 2 : Soma Sequencial
### Código Completo : Soma sequencial

```python
# Função para ler números de um arquivo texto
def ler_numeros_do_arquivo(nome_arquivo):
    with open(nome_arquivo, 'r') as arquivo:
        numeros = [int(linha.strip()) for linha in arquivo]
    return numeros

# Função para somar os números
def soma_sequencial(numeros):
    return sum(numeros)

# Nome do arquivo
nome_arquivo = 'numeros_aleatorios.txt'

# Ler os números do arquivo
numeros = ler_numeros_do_arquivo(nome_arquivo)

# Calcular a soma sequencial
resultado_soma = soma_sequencial(numeros)

print(f"Soma sequencial: {resultado_soma}")
```

### Passo 1. Definir a função `ler_numeros_do_arquivo`
    - Abre o arquivo `numeros_aleatorios.txt` em modo de leitura (`'r'`).
    - Lê cada linha do arquivo, remove espaços em branco com `strip()`, converte para inteiro e armazena na lista `numeros`.

### Passo 2. Definir a função `soma_sequencial`
    - Recebe a lista de números e retorna a soma de todos os elementos usando a função `sum()`.

### Passo 3. Definir constante com o nome do arquivo
    - Define o nome do arquivo como `numeros_aleatorios.txt`.

### Passo 4. Ler os números do arquivo
    - Chama a função `ler_numeros_do_arquivo` para ler os números do arquivo e armazená-los na variável `numeros`.

### Passo 5. Chama a função `soma_sequencial` para calcular a soma sequencial
    - Chama a função `soma_sequencial` com parâmetro `numeros` para calcular a soma dos números lidos do arquivo.

### Passo 6. Imprimir o resultado
    - Imprime o resultado da soma sequencial.



## Exemplo 2: Soma com 2 Threads

Agora, vamos dividir a soma em 2 threads.

```python
import threading

def soma_parcial(numeros, resultado, indice):
    resultado[indice] = sum(numeros)

# Dividir a lista em duas partes
metade = len(numeros) // 2
resultado = [0, 0]

# Criar duas threads
thread1 = threading.Thread(target=soma_parcial, args=(numeros[:metade], resultado, 0))
thread2 = threading.Thread(target=soma_parcial, args=(numeros[metade:], resultado, 1))

# Iniciar as threads
thread1.start()
thread2.start()

# Esperar as threads terminarem
# ponto de sincronização
thread1.join()
thread2.join()

# Soma total
soma_total = sum(resultado)
print(f"Soma com 2 threads: {soma_total}")
```

## Exemplo 3: Soma com 4 Threads

Vamos agora dividir a soma em 4 threads.

```python
# Dividir a lista em quatro partes
quarto = len(numeros) // 4
resultado = [0] * 4

# Criar quatro threads
threads = []
for i in range(4):
    inicio = i * quarto
    fim = (i + 1) * quarto if i != 3 else len(numeros)
    thread = threading.Thread(target=soma_parcial, args=(numeros[inicio:fim], resultado, i))
    threads.append(thread)

# Iniciar as threads
for thread in threads:
    thread.start()

# Esperar as threads terminarem
for thread in threads:
    thread.join()

# Soma total
soma_total = sum(resultado)
print(f"Soma com 4 threads: {soma_total}")
```

## Exemplo 4: Soma com 10 Threads

Finalmente, vamos dividir a soma em 10 threads.

```python
# Dividir a lista em dez partes
decimo = len(numeros) // 10
resultado = [0] * 10

# Criar dez threads
threads = []
for i in range(10):
    inicio = i * decimo
    fim = (i + 1) * decimo if i != 9 else len(numeros)
    thread = threading.Thread(target=soma_parcial, args=(numeros[inicio:fim], resultado, i))
    threads.append(thread)

# Iniciar as threads
for thread in threads:
    thread.start()

# Esperar as threads terminarem
for thread in threads:
    thread.join()

# Soma total
soma_total = sum(resultado)
print(f"Soma com 10 threads: {soma_total}")
```

## Conclusão

Neste exemplo, vimos como utilizar threads em Python para paralelizar a soma de um conjunto de números. Começamos com uma soma sequencial e evoluímos para somas utilizando 2, 4 e 10 threads. Isso demonstra como podemos dividir tarefas em partes menores e executá-las simultaneamente para melhorar a eficiência.

Se tiver alguma dúvida ou quiser explorar mais sobre threads, sinta-se à vontade para perguntar!
