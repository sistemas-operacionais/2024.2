# Arquiteturas de Sistemas Operacionais

## Informações gerais

- Capítulo: [Arquitetura de SO](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-03.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: wesley costa da silva
- matrícula: 20222014040017

## Respostas dos exercícios
1- O que diferencia o núcleo do restante do sistema operacional?

O núcleo, ou kernel, é a parte central do sistema operacional que gerencia diretamente os recursos de hardware e sempre roda em modo privilegiado. Já o restante do sistema operacional consiste em programas e serviços que funcionam em modo usuário, ou seja, eles têm acesso limitado e só podem interagir com o hardware através das funções que o núcleo permite.

2- Seria possível construir um sistema operacional seguro usando um processador que não tenha níveis de privilégio? Por quê?

Não seria possível, porque sem níveis de privilégio não dá para isolar as aplicações do núcleo. Isso significa que qualquer aplicação poderia acessar e controlar diretamente o hardware, o que traria sérios riscos de segurança e instabilidade para o sistema.

3- Os processadores da família x86 possuem dois bits para definir o nível de privilégio, resultando em 4 níveis distintos. A maioria dos sistemas operacionais para esses processadores usa somente os níveis extremos (0 e 3). Haveria alguma utilidade para os níveis intermediários?

Sim, os níveis intermediários poderiam ser úteis para estabelecer camadas extras de segurança ou modularidade dentro do sistema operacional. Por exemplo, alguns drivers ou serviços críticos poderiam rodar com um nível de permissão que é menos privilegiado que o núcleo, mas mais privilegiado que os aplicativos, aumentando a proteção e a organização do sistema.

4- Quais as diferenças entre interrupções, exceções e traps?

Interrupções vêm de dispositivos de hardware, como um disco ou teclado, e informam o processador sobre eventos externos. Exceções acontecem dentro do próprio processador, como erros de execução (por exemplo, uma divisão por zero). Traps são interrupções de software usadas para que um programa peça ao sistema operacional para fazer algo específico, como acessar arquivos ou dispositivos.

5- O comando em linguagem C fopen é uma chamada de sistema ou uma função de biblioteca? Por quê?

fopen é uma função de biblioteca, pois ela facilita a manipulação de arquivos, mas não lida diretamente com o hardware. Internamente, ela chama outras funções que, por sua vez, usam chamadas de sistema para interagir com o sistema de arquivos e o hardware.

6- A operação em modo usuário permite ao processador executar somente parte das instruções disponíveis em seu conjunto de instruções. Quais das seguintes operações não deveriam ser permitidas em nível usuário? Por quê?

(a) Ler uma porta de entrada/saída: não permitido – o acesso direto a dispositivos é uma operação restrita, pois poderia causar problemas de segurança.
(b) Efetuar uma divisão inteira: permitido – é uma operação básica de cálculo que não afeta a segurança do sistema.
(c) Escrever um valor em uma posição de memória: não permitido – gravar diretamente na memória pode comprometer a segurança, pois poderia acessar áreas de outros processos.
(d) Ajustar o valor do relógio do hardware: não permitido – mexer no relógio afeta o sistema como um todo e, por isso, é restrito ao núcleo.
(e) Ler o valor dos registradores do processador: não permitido – os registradores têm informações sensíveis e devem ser protegidos.
(f) Mascarar uma ou mais interrupções: não permitido – mascarar interrupções pode impedir o sistema de responder a eventos importantes, o que é perigoso.

7- Considerando um processo em um sistema operacional com proteção de memória entre o núcleo e as aplicações, indique quais das seguintes ações do processo teriam de ser realizadas através de chamadas de sistema, justificando suas respostas:

(a) Ler o relógio de tempo real do hardware: sim, precisa de acesso direto ao hardware.
(b) Enviar um pacote através da rede: sim, é necessário usar a interface de rede, controlada pelo núcleo.
(c) Calcular uma exponenciação: Não, é uma operação de cálculo que o processo pode fazer sem acessar hardware externo.
(d) Preencher uma área de memória do processo com zeros: não, o processo pode manipular sua própria memória.
(e) Remover um arquivo do disco: sim, precisa de uma chamada ao sistema de arquivos, que é gerenciado pelo núcleo.

8- Coloque na ordem correta as ações abaixo, que ocorrem durante a execução da função printf("Hello world") por um processo:

Ordem correta: h, c, d, g, a, i, j, b


1- O utilitário strace do UNIX permite observar a sequência de chamadas de sistema efetuadas por uma aplicação. Em um terminal, execute strace date para descobrir quais os arquivos abertos pela execução do utilitário date (que indica a data e hora correntes). Por que o utilitário date precisa fazer chamadas de sistema?

o date faz chamadas de sistema para acessar os arquivos necessários para obter e formatar a data e hora, interagindo com o sistema para ler configurações e permissões de acesso.

2- O utilitário ltrace do UNIX permite observar a sequência de chamadas de biblioteca efetuadas por uma aplicação. Em um terminal, execute ltrace date para descobrir as funções de biblioteca chamadas pela execução do utilitário date. Pode ser observada alguma relação entre as chamadas de biblioteca e as chamadas de sistema observadas no item anterior?

sim, as chamadas de biblioteca frequentemente usam chamadas de sistema para acessar recursos do sistema operacional. O date, por exemplo, utiliza funções de biblioteca para manipular a data e hora, que, por sua vez, acionam chamadas de sistema para interagir com o hardware e arquivos do sistema.
