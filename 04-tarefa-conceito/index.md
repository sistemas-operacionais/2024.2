# Conceito de tarefas

## Informações gerais

- Capítulo: [Conceito de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-04.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Luiz Roberto
- matrícula: 20232014040027 

## Respostas dos exercícios

1. O que significa time sharing e qual a sua importância em um sistema operacional?

R - Time Sharing é uma técnica em SO que permite multiplos usuários/processos compartilharem os recursos do sistema. A CPU divide o tempo de processamento entre todos, alternando rapidamente para dar a imperssão de uma execução simultânea. Essa técnica aumenta a eficiência do sistema, possibilitando ao usuário um tempo de resposta mais curto.

2. Como e com base em que critérios é escolhida a duração de um quantum de
processamento?

R - São 4 critérios principais:
<ul>
<li> Tipo de aplicação
<li> Carga do Sistema 
<li> Política de agendamento
<li> Desempenho do sistema
</ul>

3. Considerando o diagrama de estados dos processos apresentado na figura a
seguir, complete o diagrama com a transição de estado que está faltando (t6) e
apresente o significado de cada um dos estados e transições

R - Sei não.

4. Indique se cada uma das transições de estado de tarefas a seguir definidas é
possível ou não. Se a transição for possível, dê um exemplo de situação na qual
ela ocorre (N: Nova, P: pronta, E: executando, S: suspensa, T: terminada).

R - 
E -> P: É possível, pois o processo é retirado da CPU ao final de seu quantum
E -> S: É possível, pois ocorre quando o processo executa uma operação de I/O e entra em espera
S -> E: É possível, pois o processo retorna para execução direta
P -> N: É impossível, pois um processo ao estar pronto, não volta ao estado de novo.
S -> T: É possível, pois pode ocorrer em casos onde o processo é finalizado enquanto está suspenso
E -> T: É possível, pois o processo conclui sua execução
N -> S: É impossível, pois um processo novo não pode ir direto para o estado de suspenso
P -> S: É possível, pois pode ocorrer quando o processo aguarda um recurso específico

5. Relacione as afirmações abaixo aos respectivos estados no ciclo de vida das
tarefas (N: Nova, P: Pronta, E: Executando, S: Suspensa, T: Terminada):

R - 
[N] O código da tarefa está sendo carregado.
[P] As tarefas são ordenadas por prioridades.
[S] A tarefa sai deste estado ao solicitar uma operação de entrada/saída.
[T] Os recursos usados pela tarefa são devolvidos ao sistema.
[P] A tarefa vai a este estado ao terminar seu quantum.
[P] A tarefa só precisa do processador para poder executar.
[S] O acesso a um semáforo em uso pode levar a tarefa a este estado.
[E] A tarefa pode criar novas tarefas.
[E] Há uma tarefa neste estado para cada processador do sistema.
[S] A tarefa aguarda a ocorrência de um evento externo.