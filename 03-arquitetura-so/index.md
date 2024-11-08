# Arquiteturas de Sistemas Operacionais

## Informações gerais

- Capítulo: [Arquitetura de SO](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-03.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: 
- matrícula: 

## Respostas dos exercícios
# Exercícios

### 1. Monte uma tabela com os benefícios e deficiências mais relevantes das principais arquiteturas de sistemas operacionais.

| Arquitetura        | Benefícios                                                                                         | Deficiências                                                                                                   |
|--------------------|---------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Monolítica         | Desempenho elevado, pois os componentes interagem diretamente.                                  | Baixa robustez, pois falhas podem afetar o sistema inteiro; manutenção complicada devido a interdependências. |
| Micronúcleo        | Maior modularidade, flexibilidade e robustez, com falhas confinadas aos serviços específicos.           | Desempenho inferior, devido à troca constante de mensagens e cópia de dados entre processos.                    |
| Em Camadas         | Organização estruturada e modularidade facilitada.                                   | Redução de desempenho devido ao empilhamento de camadas; difícil de implementar devido a interdependências.      |
| Híbrida            | Combina desempenho e modularidade, trazendo componentes críticos para o núcleo.                   | Maior complexidade e possível perda de robustez em relação ao micronúcleo.                       |
| Máquinas Virtuais  | Permite múltiplos sistemas isolados em um único hardware; compatível com ambientes heterogêneos.       | Sobrecarga de virtualização, resultando em desempenho inferior à execução nativa.                          |
| Contêineres        | Isolamento eficiente de aplicações; sobrecarga menor comparado às máquinas virtuais.              | A segurança depende da integridade do núcleo compartilhado; o isolamento é menor que em VMs.              |
| Exonúcleo          | Alta eficiência e controle; permite otimização de recursos pela própria aplicação.                | Alta complexidade no desenvolvimento; ausência de abstrações comuns.                         |
| Uninúcleo          | Desempenho elevado com baixa sobrecarga nas transições; sistemas compactos para uma aplicação. | Limitações na flexibilidade e reutilização para outras aplicações e hardwares.                                |

---

### 2. O Linux possui um núcleo similar com o da figura 3.1, mas também possui “tarefas de núcleo” que executam como os gerentes da figura 3.2. Seu núcleo é monolítico ou micronúcleo? Por quê?

O núcleo do Linux é **monolítico** porque todos os componentes essenciais do sistema operam em modo núcleo, com acesso direto ao hardware e a outros componentes, como ocorre em um núcleo monolítico. Embora ele possua tarefas de núcleo que lembram os gerentes de um micronúcleo, o Linux não adota a estrutura modular do micronúcleo, onde os serviços de alto nível operam no espaço de usuário.

---

### 3. Sobre as afirmações a seguir, relativas às diversas arquiteturas de sistemas operacionais, indique quais são incorretas, justificando sua resposta:

- **(a)** Uma máquina virtual de sistema é construída para suportar uma aplicação escrita em uma linguagem de programação específica, como Java.  
  **Incorreta**. Máquinas virtuais de sistema são projetadas para executar sistemas operacionais completos, não sendo limitadas a uma linguagem de programação. Esse tipo de descrição se aplica mais a VMs de aplicação, como a JVM para Java.

- **(b)** Um hipervisor convidado executa sobre um sistema operacional hospedeiro.  
  **Correta**. Um hipervisor convidado é executado sobre um sistema operacional hospedeiro, utilizando seus recursos para criar máquinas virtuais.

- **(c)** Em um sistema operacional micronúcleo, os diversos componentes do sistema são construídos como módulos interconectados executando dentro do núcleo.  
  **Incorreta**. Em sistemas micronúcleo, componentes de alto nível são implementados fora do núcleo, no espaço de usuário, e não dentro do núcleo.

- **(d)** Núcleos monolíticos são muito utilizados devido à sua robustez e facilidade de manutenção.  
  **Incorreta**. Núcleos monolíticos são conhecidos pelo desempenho, mas não pela robustez ou facilidade de manutenção, que são, na verdade, desafios dessa arquitetura.

- **(e)** Em um sistema operacional micronúcleo, as chamadas de sistema são implementadas através de trocas de mensagens.  
  **Correta**. Em sistemas micronúcleo, as chamadas de sistema são geralmente implementadas por meio de troca de mensagens, o que possibilita maior isolamento entre processos.
