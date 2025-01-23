# Sistemas operacionais - Introdução às Threads em Python (2024.2)

## Informações gerais
- **Público alvo**: alunos da disciplina de SO (Sistemas Operacionais) do curso de TADS (Superior em Tecnologia em Análise e Desenvolvimento de Sistemas) no CNAT-IFRN (Instituto Federal de Educação, Ciência e Tecnologia do Rio Grande do Norte - Campus Natal-Central).
- disciplina: **SO** Sistemas Operacionais
- professor: [Leonardo A. Minora](https://github.com/leonardo-minora)
- texto gerado pelo [Microsoft Copilot](https://copilot.microsoft.com/)

## Conceito inicial

**Threads** são unidades de execução dentro de um processo. Elas permitem que um programa realize múltiplas operações simultaneamente, o que pode melhorar a eficiência e o desempenho, especialmente em tarefas que envolvem I/O ou operações que podem ser paralelizadas.

## Exemplo 1: Soma Sequencial

Primeiro, vamos somar 1000 números sequencialmente.

```python
import random

# Gerar uma lista de 1000 números aleatórios
numeros = [random.randint(1, 100) for _ in range(1000)]

# Soma sequencial
def soma_sequencial(numeros):
    return sum(numeros)

resultado = soma_sequencial(numeros)
print(f"Soma sequencial: {resultado}")
```

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
