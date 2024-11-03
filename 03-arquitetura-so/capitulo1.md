# Arquiteturas de Sistemas Operacionais

## Informações gerais

- Capítulo: [Arquitetura de SO](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-03.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: wesley costa da silva
- matrícula: 20222014040017

## Respostas dos exercícios

1-Quais os dois principais objetivos de um sistema operacional?

o sistema operacional tem dois grandes objetivos principais: fornecer uma abstração dos recursos de hardware, o que facilita a criação de aplicativos ao esconder a complexidade dos dispositivos, e gerenciar esses recursos, distribuindo-os de forma organizada e eficiente para evitar conflitos entre os programas.

2-Por que a abstração de recursos é importante para os desenvolvedores de aplicações? Ela tem alguma utilidade para os desenvolvedores do próprio sistema operacional?

A abstração simplifica muito o trabalho dos desenvolvedores, já que eles não precisam lidar com as particularidades de cada dispositivo. Por exemplo, ao invés de aprender a controlar cada tipo de disco rígido, o programador usa uma interface genérica de "arquivos" que funciona da mesma forma em qualquer dispositivo de armazenamento. Para os desenvolvedores do próprio sistema operacional, a abstração também facilita a implementação, permitindo que o sistema ofereça uma interface mais estável e independente do hardware subjacente.

3-A gerência de tarefas permite compartilhar o processador, executando mais de uma aplicação ao mesmo tempo. Identifique as principais vantagens trazidas por essa funcionalidade e os desafios a resolver para implementá-la.

a principal vantagem é que o processador consegue atender várias tarefas ao mesmo tempo, proporcionando ao usuário a experiência de multitarefa e melhorando o uso geral do sistema. O desafio está em fazer o escalonamento adequado das tarefas, para que nenhuma fique “presa” esperando o processador, garantindo que tudo funcione de forma suave e rápida para o usuário.

4-O que caracteriza um sistema operacional de tempo real?

Sistemas de tempo real são projetados para responder dentro de um tempo fixo e previsível, algo essencial em situações onde a resposta rápida é crítica. Em sistemas de tempo real “hard”, uma resposta atrasada pode causar sérios problemas, enquanto em sistemas “soft”, um pequeno atraso apenas degrada o serviço.

5-Associe as categorias de sistemas operacionais aos seus usos ou características típicas.

Tempo Real: Ideal para aplicações com necessidade de respostas previsíveis, como controle industrial.
Servidor: Usado para gerenciar grandes volumes de dados e atender a muitos usuários em rede.
Embarcado: Feito para dispositivos específicos como smartphones ou equipamentos industriais.
Distribuído: Permite que recursos de vários computadores sejam usados como se fossem um só.
Multiusuário: Controla o acesso a recursos e permite que muitos usuários compartilhem o sistema.
Móvel: Prioriza a eficiência energética e a conectividade para dispositivos portáteis.

6-Sobre as afirmações a seguir, relativas aos diversos tipos de sistemas operacionais, indique quais são incorretas:

(a) correta
(b) correta
(c) incorreta
(d) incorreta
(e) correta
