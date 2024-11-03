# Arquiteturas de Sistemas Operacionais

## Informações gerais

- Capítulo: [Arquitetura de SO](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-03.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: wesley costa da silva
- matrícula: 20222014040017

## Respostas dos exercícios
1- Monte uma tabela com os benefícios e deficiências mais relevantes das principais arquiteturas de sistemas operacionais.

Monolítica: Tem o benefício de ser bem rápida, porque todos os componentes do sistema estão integrados e podem se comunicar diretamente. Mas o lado ruim é que, se algo der errado em um dos componentes, isso pode acabar afetando todo o sistema, além de ser mais difícil de manter.

Micronúcleo: Esse tipo de núcleo é bem modular, o que aumenta a estabilidade, já que as partes ficam mais isoladas – se um serviço falhar, o resto do sistema continua funcionando. Só que, por outro lado, essa separação entre componentes acaba deixando o sistema mais lento, porque tudo precisa se comunicar por meio de mensagens.

Em camadas: Estruturar o sistema em camadas ajuda a organizar e modularizar tudo direitinho, então é fácil de entender e manter. A desvantagem é que a comunicação entre as várias camadas pode diminuir o desempenho do sistema.

Híbrida: Tenta combinar o melhor dos dois mundos, trazendo a modularidade do micronúcleo, mas mantendo o desempenho do núcleo monolítico para os componentes críticos. O problema é que esse tipo de núcleo pode ser bem mais complexo de implementar e manter.

2- O Linux possui um núcleo similar com o da figura 3.1, mas também possui “tarefas de núcleo” que executam como os gerentes da figura 3.2. Seu núcleo é monolítico ou micronúcleo? Por quê?

O núcleo do Linux é considerado monolítico. Embora ele permita carregar e descarregar módulos, a maior parte dos serviços do sistema funciona diretamente no núcleo para melhorar o desempenho. Essa característica é típica de núcleos monolíticos, mesmo que o Linux tenha alguma modularidade.

3- Sobre as afirmações a seguir, relativas às diversas arquiteturas de sistemas operacionais, indique quais são incorretas, justificando sua resposta:

(a)incorreta: Máquinas virtuais de sistema são feitas para rodar sistemas completos, não uma aplicação específica como Java.

(b)correta: Um hipervisor convidado realmente roda em cima de um sistema operacional hospedeiro, então essa está certa.

(c)incorreta: Em um sistema micronúcleo, os componentes principais rodam fora do núcleo e se comunicam com ele através de mensagens, ou seja, eles não ficam todos dentro do núcleo.

(d)incorreta: Núcleos monolíticos não são fáceis de manter – uma falha em qualquer parte pode afetar o sistema inteiro, o que dificulta a manutenção.

(e) correta: Em micronúcleos, as chamadas de sistema são feitas através de trocas de mensagens, o que ajuda a isolar as falhas e manter tudo modular.