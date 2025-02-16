# Conceito de tarefas

## Informações gerais

- Capítulo: [Conceito de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-04.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Wesley costa da silva 
- matrícula: 20222014040017

## Respostas dos exercícios
# Exercícios

### 1. O que significa *time-sharing* e qual a sua importância em um sistema operacional?

*Time-sharing* é a ideia de dividir o tempo do processador entre várias tarefas. Cada tarefa recebe um tempo específico para rodar (chamado de *quantum*), e quando esse tempo acaba, o sistema pausa essa tarefa e passa para a próxima. Esse mecanismo permite que o computador pareça estar executando várias tarefas ao mesmo tempo, o que melhora a eficiência e a experiência do usuário.

---

### 2. Como e com base em que critérios é escolhida a duração de um *quantum* de processamento?

O tempo do *quantum* é ajustado de acordo com o tipo de tarefa e o quanto o sistema precisa responder rápido. Em sistemas interativos, como computadores pessoais e smartphones, o *quantum* costuma ser mais curto para que as respostas sejam rápidas. Em servidores, onde o foco é processar grandes volumes de dados, o *quantum* é geralmente mais longo, para evitar trocas de contexto frequentes e aproveitar melhor o processador.

---



### 4. Indique se cada uma das transições de estado de tarefas a seguir definidas é possível ou não. Se a transição for possível, dê um exemplo de situação na qual ela ocorre (N: Nova, P: Pronta, E: Executando, S: Suspensa, T: Terminada).

- **E → P**: Possível. Acontece quando a tarefa executa até o final de seu *quantum* e volta para a fila de prontas.
- **E → S**: Possível. Acontece quando uma tarefa em execução precisa aguardar algum recurso, como dados do disco, e é suspensa.
- **S → E**: Possível. Quando o recurso necessário fica disponível, a tarefa é retomada e começa a rodar.
- **P → N**: Impossível. Uma tarefa que está pronta já foi criada e carregada na memória, então ela não pode voltar a ser "nova".
- **S → T**: Impossível. Uma tarefa suspensa não termina enquanto não passa pela execução novamente.
- **E → T**: Possível. Acontece quando a tarefa completa sua execução ou é encerrada devido a um erro.
- **N → S**: Impossível. Uma tarefa precisa estar carregada e pronta antes de poder ser suspensa.
- **P → S**: Possível. Quando uma tarefa pronta é forçada a esperar por um evento ou recurso antes de continuar.

---

### 5. Relacione as afirmações abaixo aos respectivos estados no ciclo de vida das tarefas (N: Nova, P: Pronta, E: Executando, S: Suspensa, T: Terminada):

- [N] O código da tarefa está sendo carregado.
- [P] As tarefas são ordenadas por prioridades.
- [E] A tarefa sai deste estado ao solicitar uma operação de entrada/saída.
- [T] Os recursos usados pela tarefa são devolvidos ao sistema.
- [P] A tarefa vai a este estado ao terminar seu *quantum*.
- [P] A tarefa só precisa do processador para poder executar.
- [S] O acesso a um semáforo em uso pode levar a tarefa a este estado.
- [E] A tarefa pode criar novas tarefas.
- [E] Há uma tarefa neste estado para cada processador do sistema.
- [S] A tarefa aguarda a ocorrência de um evento externo.
