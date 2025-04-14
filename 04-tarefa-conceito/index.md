# Conceito de tarefas

## Informações gerais

- Capítulo: [Conceito de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-04.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Gustavo Henrique da Cruz Maciel
- matrícula: 20232014040003

## Respostas dos exercícios

1) Time-sharing é um método que permite a execução simultânea de múltiplos processos ao compartilhar o tempo do processador entre eles. É importante porque melhora a interatividade em sistemas multitarefa, permitindo que os usuários percebam respostas rápidas mesmo em ambientes compartilhados.

##
2)
- **Interatividade**: Quanta mais curtos são melhores para sistemas interativos.
- **Sobrecarga**: Quanta muito curtos podem aumentar o overhead causado pelas trocas de contexto.
- **Tipo de aplicação**: Sistemas de tempo real podem exigir quanta específicos para garantir deadlines.
  
##
3) **t6(Encerramento)**: Executando → Encerrado.

##
4) 
- **E→P**: Possível (ex.: preempção do processo).
- **E→S**: Possível (ex.: operação de E/S bloqueante).
- **S→E**: Possível (ex.: operação de entrada/saída concluída).
- **P→N**: Impossível (um processo pronto não pode voltar ao estado inicial).
- **S→T**: Impossível (um processo suspenso deve passar por pronto/executando para terminar).
- **E→T**: Possível (ex.: conclusão de execução).
- **N→S**: Impossível (processo novo não pode ser diretamente suspenso).
- **P→S**: Possível (ex.: bloqueio explícito).

##
5)
**N**: [X] O código da tarefa está sendo carregado. [ ] A tarefa pode criar novas tarefas.

**P**: [ ] A tarefa só precisa do processador para poder executar. [X] A tarefa vai a este estado ao terminar seu quantum.

**E**: [X] Há uma tarefa neste estado para cada processador do sistema. [X] A tarefa só precisa do processador para poder executar.

**S**: [X] O acesso a um semáforo em uso pode levar a tarefa a este estado. [X] A tarefa aguarda a ocorrência de um evento externo.

**T**: [X] Os recursos usados pela tarefa são devolvidos ao sistema.
