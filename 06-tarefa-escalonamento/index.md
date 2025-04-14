# Escalonamento de tarefas

## Informações gerais

- Capítulo: [Escalonamento de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-06.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Luiz Roberto
- matrícula: 20232014040027

## Respostas dos exercícios

1. Explique o que é escalonamento round-robin, dando um exemplo.

R - 
O Round-Robin é uma técnica de escalonamento que utiliza um tempo fixo para execução de cada tarefa. As  tarefas são colocadas em uma fila circular e o escalonador aloca o processador a cada uma por uma fatia de tempo.

2. Considere um sistema de tempo compartilhado com valor de quantum tq e
duração da troca de contexto ttc. Considere tarefas de entrada/saída que usam
em média p% de seu quantum de tempo cada vez que recebem o processador.
Defina a eficiência E do sistema como uma função dos parâmetros tq, ttc e p.

R - 
Além de não conseguir, não tem como colocar aqui totalmente.

3. Explique o que é, para que serve e como funciona a técnica de aging

R - 
Aging é uma técnica de escalonamento usado para evitar o problema de starvation, no qual os processos de baixa prioridade esperam indefinidamente por execução. A técnica funciona aumentando a prioridade de processos que estão esperando na fila, periodicamente o sistema incremenda a prioridade desses processos na fila de espera, esse incremento ocorre até que o processo obtenha prioridade suficiente para competir com outros de maior prioridade

4. No algoritmo de envelhecimento definido na Seção 6.4.6, o que seria necessário
modificar para suportar uma escala de prioridades negativa?

R - 
Para suportar uma escala de prioridade negativa, o algoritmo precisa ser modificado para que as prioridades mais altar indiquem processos com maior prioridade. Nesse caso, ao invés de incrementar a prioridade, deve-se diminuir a prioridade numérica ao logo do tempo para indicar o envelhecimento do processo.

5. A tabela a seguir representa um conjunto de tarefas prontas para utilizar um
processador:

R - 

6. Idem, para as tarefas da tabela a seguir:

R - 