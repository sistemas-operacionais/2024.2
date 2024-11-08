# Implementação de tarefas

## Informações gerais

- Capítulo: [Implementação de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-05.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: wesley costa da silva 
- matrícula: 20222014040017

## Respostas dos exercícios
# Exercícios

### 1. Explique o que é, para que serve e o que contém um TCB - Task Control Block.

O TCB é uma estrutura de dados que guarda informações de cada tarefa, como o estado (pronta, executando), registradores e recursos usados. Ele permite que o sistema pause e retome as tarefas quando necessário.

---

### 3. Indique quantas letras “X” serão impressas na tela pelo programa abaixo quando for executado com a linha de comando `a.out 4 3 2 1`.

A quantidade de letras "X" impressas depende dos processos criados com `fork()`. Cada `fork()` duplica o processo, então várias "X" serão impressas.

---

### 4. O que são threads e para que servem?

Threads são fluxos de execução independentes dentro de um processo, usadas para executar tarefas simultâneas. Elas ajudam a dividir o trabalho em paralelo, acelerando o processamento.

---

### 5. Quais as principais vantagens e desvantagens de threads em relação a processos?

- **Vantagens**: Criação rápida e fácil compartilhamento de dados.
- **Desvantagens**: Menor segurança e robustez, pois um erro numa thread pode afetar as outras.

---

### 6. Forneça dois exemplos de problemas cuja implementação multi-thread não tem desempenho melhor que a respectiva implementação sequencial.

1. Algoritmos sequenciais, onde cada etapa depende da anterior.
2. Acesso intenso a um único recurso compartilhado, como um arquivo ou banco de dados.

---

### 7. Associe as afirmações a seguir aos seguintes modelos de threads: a) many-to-one (N:1); b) one-to-one (1:1); c) many-to-many (N:M):

(a) **N:1**  
(b) **N:M**  
(c) **1:1**  
(d) **N:1**  
(e) **N:M**  
(f) **N:1**  
(g) **1:1**  
(h) **N:1**  
(i) **1:1**  
(j) **N:M**
