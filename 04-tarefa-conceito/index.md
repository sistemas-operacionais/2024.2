# Conceito de tarefas

## Informações gerais

- Capítulo: [Conceito de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-04.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Robson Douglas Fernandes de Araújo
- matrícula: 20231014040036

## Respostas dos exercícios

1- É uma técnica utilizada em sistemas operacionais para permitir que múltiplos usuários ou tarefas acessem o sistema de forma aparentemente simultânea. O sistema operacional usa um scheduler para decidir a ordem e a duração em que cada processo ou tarefa terá acesso ao processador. A alternância rápida entre as tarefas cria a ilusão de que estão sendo executadas ao mesmo tempo, mesmo em um sistema de apenas um processador. O time sharing aumenta a produtividade, melhora a responsividade, gerencia recursos eficientemente e cuida do isolamento e segurança de forma melhorada.

2- Quantum de processamento é o intervalo de tempo em que um processo tem acesso exclusivo ao processador antes que o sistema operacional realize uma troca de contexto e passe a execução para outro processo. Ele leva em consideração critérios como a responsividade, o tipo de tarefas sendo executadas e o desempenho global do sistema

3- 
e1: nova; e2: terminada; e3: executando; e4: suspensa; e5: pronta
o t6 é de e3 para e5, ou seja, executando -> pronta

4- E → P: sim; E → S: sim; S → E: não; P → N: não; S → T: não; E → T: sim; N → S: não; P → S: não;

5- 
N
P
P
T
T
N
S
E
P
S
