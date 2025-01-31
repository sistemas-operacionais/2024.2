# Arquiteturas de Sistemas Operacionais

## Informações gerais

- Capítulo: [Arquitetura de SO](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-03.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Robson Douglas Fernandes de Araújo
- matrícula: 20231014040036

## Respostas dos exercícios

1- 
Sistemas monolíticos
Benefícios: opera com acesso a todos os recursos do hardware e sem restrições de acesso à memória; desempenho eficiente, onde qualquer componente do núcleo pode acessar os outros componentes, áreas de memória e dispositivos periféricos.
Deficiências: caso um componente falhe, isso pode se propagar e afetar os outros, causando travamento ou reinicialização; a manutenção e evolução do núcleo são complexas por causa da interdependência entre os componentes.

Sistemas micronúcleo
Benefícios: cada serviço pode funcionar independentemente dos demais, podendo ser inicializados ou finalizados conforme necessário; quando um serviço falha, ele não interfere nos outros, fazendo com que o sistema seja flexível e robusto.
Deficiências: cada chamada de sistema implica no fluxo de execução e reconfiguração do acesso à memória, fazendo com que hajam várias cópias de dados entre as áreas de memória de cada entidade, isso torna o desempenho bem inferior ao sistema monolítico.

Sistemas em camadas
Benefícios: define uma divisão de funcionamento entre interface com o hardware (camada baixa), abstração e gerência (camadas intermediárias) e interface do núcleo para as aplicações (camada superior). 
Deficiências: as funcionalidades são interdependentes, então não há como organizar algumas delas em forma de camadas; a utilização das camadas de software faz com que os pedidos de aplicação levem um certo tempo para realizar seus trajetos, o que acaba afetando o desempenho do sistema.

Sistemas híbridos
Benefícios: abordagem intermediária entre o núcleo monolítico e micronúcleo; traz de volta ao núcleo os componentes mais críticos, obtendo melhor desempenho.
Deficiências: ---

Máquinas virtuais
Benefícios:  usa os serviços de um sistema operacional convencional (Windows ou Linux) para construir um computador virtual que processa bytecode; o ambiente VMWare permite executar o sistema Windows sobre um sistema Linux, ou vice-versa.
Deficiências: ---

Contêineres
Benefícios: o espaço de usuário do sistema operacional é dividido em áreas isoladas denominadas domínios ou contêineres. A cada domínio é alocada uma parcela dos recursos do sistema operacional, como memória, tempo de processador e espaço em disco.
Deficiências: processos em domínios distintos não podem ver ou interagir entre si; processos não podem trocar de domínio nem acessar recursos de outros domínios; os domínios são vistos como sistemas distintos, acessíveis somente através de seus endereços de rede.

Sistemas exonúcleo
Benefícios: o núcleo do sistema apenas proporciona acesso controlado aos recursos do hardware, mas não implementa nenhuma abstração.
Deficiências: todas as abstrações e funcionalidades de gerência que uma aplicação precisa terão de ser implementadas pela própria aplicação, em seu espaço de memória.

Sistemas uninúcleo
Benefícios: o custo da transição aplicação/núcleo nas chamadas de sistema diminui muito, gerando um forte ganho de desempenho.
Deficiências: estrutura de uninúcleo se mostra adequada geralmente apenas para computadores que executam uma única aplicação.


2-
Monolítico, porque a maioria de suas funcionalidades e serviços do sistema são executados no próprio kernel, em um único espaço de memória com acesso direto ao hardware, embora o linux tenha evoluído para ser modular, permitindo a inclusão de módulos no kernel sem a necessidade de recompilação.

3-
a) errada, uma máquina virtual não se limita a suportar aplicações específicas ou linguagens de programação.
b) certa
c) errada, o núcleo é responsável apenas pelas funções essenciais, os outros serviços do sistema são executados fora do núcleo, em espaço de usuário.
d) errada, a manutenção de núcleos monolíticos é geralmente mais complexa, já que qualquer falha em um componente pode comprometer todo o sistema.
e) certa
