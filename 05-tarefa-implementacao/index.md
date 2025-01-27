# Implementação de tarefas

## Informações gerais

- Capítulo: [Implementação de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-05.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Robson Douglas Fernandes de Araújo
- matrícula: 20231014040036

## Respostas dos exercícios

1 - é uma estrutura de dados fundamental em sistemas operacionais multitarefa, responsável por armazenar informações essenciais sobre um ou processo em execução. Possui um identificador da tarefa; estado da tarefa; informações de contexto do processador; lista de áreas de memória usadas pela tarefa; listas de arquivos abertos; conexões de rede e outros recursos usados pela tarefa; e informações de gerência e contabilização. Ele serve como uma "ficha" completa do processo que o sistema operacional consulta e atualiza conforme o processo se move entre estados.

2 - valor de x = 2; duração aproximada de 10 segundos.

3 - 4: XXXXXXXXXXXXXXX; 3: XXXX; 2: XX; 1: XXX

4 - São as menores unidades de processamento que podem ser executadas por um sistema operacional. Elas representam uma linha de execução independente que permite ao programa realizar várias tarefas ao mesmo tempo. São usadas para realizar operações simultâneas ou assíncronas e são essenciais para uma ampla gama de aplicações, especialmente aquelas que demandam performance e responsividade, a utilização de threads é especialmente útil para melhorar a performance de programas.

5 - A implementação de sistemas usando um processo para cada tarefa  tem como grande vantagem a robustez, pois um erro
ocorrido em um processo ficará restrito ao seu espaço de memória pelos mecanismos de isolamento do hardware. Além disso, os processos podem ser configurados para executar com usuários (e permissões) distintas, aumentando a segurança do sistema.
Também é possível implementar todas as tarefas em um único processo, usando uma thread para cada tarefa. Neste caso, todas as threads compartilham o mesmo espaço de endereçamento e os mesmos recursos (arquivos abertos, conexões de rede, etc), tornando mais simples implementar a interação entre as tarefas. Além disso, a execução é mais ágil, pois é mais rápido criar uma thread que um processo. Todavia, um erro em uma thread pode se alastrar às demais, pondo em risco a robustez da aplicação inteira.
Sistemas mais recentes e sofisticados usam uma abordagem híbrida, com o uso
conjunto de processos e threads.

6 - 1) Para cálculos que possuem uma alta dependência de dados sequenciais, como algoritmos recursivos, a implementação multi-thread normalmente não oferece vantagens de desempenho. 2) Operações de entrada ou saída sequenciais, como a leitura de um arquivo grande ou um banco de dados onde o conteúdo deve ser processado em ordem específica.

7 - 
a) N:1
b) N:M
c) 1:1
d) N:1
e) N:M
f) N:1
g) 1:1
h) N:1
i) 1:1
j) N:M

8 - 
a) ---
b) Duração de execução em torno de 12-13 segundos.
c) 
x = 1, y: 1
x = 1, y: 2
x = 1, y: 3
