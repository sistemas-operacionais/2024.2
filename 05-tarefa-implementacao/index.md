# Implementação de tarefas

## Informações gerais

- Capítulo: [Implementação de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-05.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Luiz Roberto
- matrícula: 20232014040027

## Respostas dos exercícios

1. Explique o que é, para que serve e o que contém um TCB - Task Control Block

R - O TCB(Task Control Block), é uma estrutura de dados usada por SO para armazenar informações essenciais sobre cada processo que está em execução. Ele serve como um repositório de informações para gerenciar o controle de processos no sistema.

2. Desenhe o diagrama de tempo da execução do código a seguir, informe qual a
saída do programa na tela (com os valores de x) e calcule a duração aproximada
de sua execução.

R - 

3. Indique quantas letras “X” serão impressas na tela pelo programa abaixo quando
for executado com a seguinte linha de comando:

R - 

4. O que são threads e para que servem?

R - Threads são subunidades de execução de um processo, permitem que tarefas dentro do mesmo programa sejam executadas simultaneamente. Elas são usadas para melhorar o desempenho de programas que podem realizar operações paralelas.

5. Quais as principais vantagens e desvantagens de threads em relação a processos?

R - Entre as vantagens das Threads, estão o compartilhamento de memória, ja que threads de um mesmo processo compartilham memória, reduzindo o custo de troca de contexto e a rapidez, ja que a criação e térmido de threads são geralmente mais rápidos do que processos. Já dentre as desvantagens estão a sincronização, ja que o compartilhamento de memória exige mecanismos de sincronização e o bloqueio, pois se uma thread bloqueia, pode afetar outras threads do mesmo processo.

6. Forneça dois exemplos de problemas cuja implementação multi-thread não tem
desempenho melhor que a respectiva implementação sequencial.

R - 
Processamento Sequencial de Arquivos: Em uma leitura sequencial, a criação de threads pode sobrecarregar
Cálculo de Fibonacci Recursivo: O cálculo é dependente de valores anteriores e, com muitas threads, pode piorar devido à competição por recursos.

7. Associe as afirmações a seguir aos seguintes modelos de threads: a) many-to-one
(N:1); b) one-to-one (1:1); c) many-to-many (N:M):

R - 
(a) N:1
(b) N
(c) 
(d) N:1
(e) 
(f) N:1
(g) 
(h) N:1
(i) 
(j) N

8. Considerando as implementações de threads N:1 e 1:1 para o trecho de código a
seguir, a) desenhe os diagramas de execução, b) informe as durações aproximadas de execução e c) indique a saída do programa na tela. Considere a operação
sleep() como uma chamada de sistema (syscall

R - ?