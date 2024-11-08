# Escalonamento de tarefas

## Informações gerais

- Capítulo: [Escalonamento de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-06.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Wesley costa da Silva 
- matrícula: 20222014040017

## Respostas dos exercícios
# Exercícios Capítulo 6

### 1. Explique o que é escalonamento round-robin, dando um exemplo.

O escalonamento *round-robin* é uma técnica que distribui o processador de forma circular entre as tarefas. Cada tarefa recebe um tempo fixo, chamado de *quantum*. Quando o tempo de uma tarefa acaba, ela vai para o final da fila e a próxima começa a executar. Por exemplo, com um *quantum* de 2 segundos, uma sequência de três tarefas (`T1`, `T2`, `T3`) seria executada em ciclos de 2 segundos para cada uma, de forma alternada, até que todas terminem.

---


### 3. Explique o que é, para que serve e como funciona a técnica de aging.

O *aging* (ou envelhecimento) é uma técnica que aumenta a prioridade das tarefas que estão esperando há muito tempo, evitando que fiquem em inanição (*starvation*). Assim, conforme uma tarefa espera, sua prioridade é gradualmente aumentada até que ela seja executada, garantindo que todas as tarefas recebam tempo de processamento.

---

### 4. No algoritmo de envelhecimento definido na Seção 6.4.6, o que seria necessário modificar para suportar uma escala de prioridades negativa?

Para adaptar o envelhecimento para uma escala de prioridades negativa, o sistema deve aumentar gradualmente o valor da prioridade negativa das tarefas mais antigas, fazendo com que elas se aproximem de zero ao longo do tempo. Isso permitiria que uma tarefa com baixa prioridade (valor negativo alto) subisse até um ponto em que pudesse ser executada.
