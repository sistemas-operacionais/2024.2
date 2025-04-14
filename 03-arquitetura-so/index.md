# Arquiteturas de Sistemas Operacionais

## Informações gerais

- Capítulo: [Arquitetura de SO](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-03.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Gustavo Henrique da Cruz Maciel
- matrícula: 20232014040003

## Respostas dos exercícios
1)
1. Monolítica:
     - Benefícios: Alta performance, interação direta entre componentes.
     -Deficiências: Complexidade na manutenção e depuração.

2. Micronúcleo:
     - Benefícios: Maior segurança, modularidade, facilidade de manutenção.
     - Deficiências: Desempenho inferior devido à troca de mensagens.
 
3. Híbrida:
     - Benefícios: Combina desempenho (monolítica) e modularidade (micronúcleo).
     - Deficiências: Maior complexidade de implementação.
   
4. Máquinas Virtuais:
     - Benefícios: Isolamento, suporte a múltiplos sistemas no mesmo hardware.
     - Deficiências: Overhead de virtualização.

##
2) O núcleo do Linux é monolítico, pois todo o código do sistema operacional, incluindo gerentes de sistema, dispositivos, gerência de memória e sistema de arquivos, é executado no modo núcleo. Apesar disso, ele adota modularidade para carregar ou descarregar partes do sistema, mas ainda funciona como núcleo monolítico devido à falta de isolamento entre os componentes.

##
3)
- (a) Incorreta: Máquinas virtuais de sistema virtualizam um hardware completo, enquanto aquelas voltadas para linguagens específicas, como Java, são máquinas virtuais de aplicação.
- (b) Correta: Hipervisores convidados podem executar sobre sistemas operacionais hospedeiros (ex.: VMware Workstation).
- (c) Incorreta: Em sistemas micronúcleo, os componentes não executam todos dentro do núcleo; muitos são executados no modo de usuário.
- (d) Incorreta: Núcleos monolíticos não são fáceis de manter, sendo mais propensos a bugs devido à sua complexidade.
- (e) Correta: Em micronúcleos, chamadas de sistema frequentemente utilizam trocas de mensagens entre processos no núcleo e no espaço de usuário.

##
