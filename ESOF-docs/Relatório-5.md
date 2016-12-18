# Relatório 5



<a name="index">
## Índice


1. [Introdução](#introduction)
2. [Métricas SIG](#metricas)
3. [*Feature*](#feature)
  1. [Identificação da *feature*](#idFeature)
  2. [Implementação da *feature*](#impFeature)
  3. [*Pull Request*](#pull)
4. [Conclusão e análise crítica](#conclusion)
5. [Links externos](#links)
6. [Contribuições](#contributions)
7. [Identificação do grupo](#idGrupo)


<a name="introduction">
## Introdução


Em engenharia de *software*, manutenção ou evolução de *software* é o processo de melhoria e otimização de um *software* já desenvolvido, assim como a correção de defeitos que possam existir. 
A [manutenção de *software*](https://pt.wikipedia.org/wiki/Manuten%C3%A7%C3%A3o_de_software) propriamente dito é uma das [fases do processo de desenvolvimento de software](https://pt.wikipedia.org/wiki/Processo_de_desenvolvimento_de_software), ocorrendo seguidamente à entrada do *software* em produção. Esta fase envolve:

-	Mudanças no *software* para corrigir defeitos e/ou deficiências encontradas aquando da utilização por parte do utilizador
- Novas funcionalidades (*features*) para melhorar a aplicabilidade e [usabilidade](https://pt.wikipedia.org/wiki/Usabilidade) do *software*

Sendo o **BetterStorage** um projeto *openSource*, apesar de já se encontrar um pouco descontinuado, qualquer novo contribuidor deve dialogar com a equipa de *developers*, acerca de possíveis mudanças a executar no projeto, de forma a que estas sejam úteis e com um grau de dificuldade acessível para novos *developers*, que não conhecem com exatidão o mesmo.

Neste relatório, está presente uma breve descrição relativa às **métricas SIG**, obtidas através do ***BetterCodeHub***, assim como uma referência à *feature* implementada, recaindo sobre a sua descrição, desenvolvimento e *pull request*. No fim, está ainda expressa, como habitualmente, uma conclusão retirada ao longo do desenvlvimento deste relatório.


<a name="metricas">
## Métricas SIG


Para a análise das **métricas SIG**, foi-nos proposto o uso de uma ferramenta capaz de verificar a possibilidade de manutenção do **BetterStorage** e, igualmente, avaliar a qualidade do projeto, desenvolvido até ao momento da implementação da *feature*.

Os pontos chave avaliados recaem sobre:

- Escrever pequenas porções de código
- Escrever porções simples de código
- Evitar código repetido
- Manter as interfaces pequenas
- Separar funcionalidades em módulos
- Arquitetura com componentes independentes
-	Manter as componentes arquiteturais equilibradas
-	Manter a base de código pequena
-	Testes automatizados
-	Desenvolvimento de código estruturado e otimizado


Após analisar o código do **BetterStorage** usando o [***BetterCodeHub***]( https://bettercodehub.com/results/VascoUP/BetterStorage), verificámos que somente **60%** das métricas de avaliação, ou seja **6** em **10** parâmetros, é que obtiveram aprovação.

As métricas que não obtiveram aprovação recaem em:

- Escrever porções simples de código
- Manter as interfaces pequenas
-	Manter as componentes arquiteturais equilibradas
-	Testes automatizados



<p align="center">
  <img src='https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/betterCode.png'>
</p>
<p align="center">Figura 1 - Resultados obtidos ao analisar o projeto</p>



Assim, apercebemo-nos que o **BetterStorage** por ser um projeto *openSource* necessita de ser um projeto bem organizado e com uma estrutura que permita com que os novos colaboradores possam compreender o que se passa naquele trabalho, de forma a que estes possam contribuir sempre da melhor forma possível.

O **BetterStorage**, de facto, possui fragmentos pequenos de código, o que faz com que possam ser mais facilmente compreendidos, utilizados somente para uma certa finalidade. Contudo estes não são desenvolvidos de forma simples.

Para além disso, o **BetterStorage** está bem dividido em módulos, com um grande grau de independência, podendo-os isolar mais facilmente, mostrando assim ter uma arquitetura sólida. Apesar disso, os componentes arquiteturais não estão equilibrados, o que faz com que haja diferente número de componentes distribuídos pelos diferentes módulos, fazendo com que seja mais complicada a localização de certas porções de código. Mesmo alterando o nível de profundidade dos componentes através do ficheiro [.bettercodehubyml](https://github.com/VascoUP/BetterStorage/blob/master/.bettercodehubyml), nível de profundidade este em que utilizámos diversos valores, não se conseguiu uma aprovação relativa ao equilíbrio dos componentes arquiteturais.

Ainda, verificou-se que as interfaces do projeto não são pequenas, pois diversos métodos do **BetterStorage** necessitam de muitos argumentos, o que faz com que esta avaliação esteja correta. Uma quantidade reduzida de argumentos torna a utilização das funções mais intuitiva, facilitando a manutenção dos componentes respetivos. 

Por fim, verificou-se que este projeto tem uma base de código pequena e código que o torna bem estruturado e otimizado, o que melhora a manutenção do mesmo, já que uma base de código menor faz com que seja menor o trabalho ao fazer mudanças estruturais.

De referir ainda, que a métrica referente aos testes automáticos não recebeu aprovação, uma vez que este projeto não contém quaisquer módulos de testes, sendo impossível analisar assim tal métrica.

De seguida, pode-se visualizar o *badge* atribuído ao projeto.



<p align="center">
  <img src='https://bettercodehub.com/edge/badge/VascoUP/BetterStorage'>
</p>
<p align="center">Figura 2 - Badge do projeto</p>



<a name="feature">
## *Feature*


<a name="idFeature">
### Identificação da *feature*


De forma a adicionar novas funcionalidades ao nosso *mod*, poderíamos ter-nos direcionado em três sentidos. Um deles seria adicionar uma completa nova funcionalidade que pouco tivesse haver com o principal foco do *mod*: **o aumento da diversidade de armazenamento de itens**. Outra seria somente tentarmos resolver as [*issues*](https://github.com/copygirl/BetterStorage/issues) já encontradas no **BetterStorage**, ou então, poderiamos tentar adicionar algo semelhante ao já existente, mas com pequenas mudanças. 

Optámos, assim, pela que mais lógica tinha para nós, ou seja, a terceira hipótese, e assim implementámos um novo tipo de armazenamento de itens, o **cardboardBackpack**.

Este novo item, teve como base outros itens já existentes, o que fez com que conseguissemos compreender melhor o funcionamento da criação de novos itens no jogo *MineCraft*, em especial no nosso *mod*, **BetterStorage**. Utilizou-se, assim, o *backpack* e *enderBackpack* para criar o nosso **cardboardBackpack**, que consiste num item de armazenamento feito de cartão, com uma nova aparência, em relação aos itens já criados pelo *mod*.



<p align="center">
  <img src='https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/BackpackEquiped.png'>
</p>
<p align="center">Figura 3 - Item de armazenamento criado pelo grupo</p>



<a name="impFeature">
### Implementação da *feature*


Inicialmente, foi necessário identificar os módulos que o **BetterStorage** usa para criar um item/bloco no jogo.

De seguida, com base nos itens já existentes, *backpack* e *enderBackpack*, criaram-se os ficheiros necessários e fizeram-se alterações ao código original para se obter um item semelhante aos anteriores.

Depois disto, foi uma questão de mudar o aspecto gráfico da **cardboardBackpack** criada (textura e nome **in-game**), assim como modificar as suas características internas, como por exemplo a receita de construção, para que tudo correspondesse às nossas ideias.

Toda a implementação da *feature* foi feita com alguma facilidade, uma vez que a *cardboardBackpack* se baseava em itens já existentes, tendo sido testada já em ambiente de jogo, contendo no entando dois aspetos, que o grupo não conseguiu solucionar, uma vez que não conseguimos encontrar o local no código onde poderiamos mudar tais pormenores, pormenores estes que não inviabilizam a utilização do item de armazenamento no jogo. Um desses "problemas" recai sobre o facto da *cardboardBackpack* não ter um *icon* no inventário do *mod* e o outro "problema" é relativo ao facto do item ter no fim do seu nome uma extensão **.name**.

Como se pode ver de seguida, o item *cardboardBackpack* pode ser jogado como qualquer outro item do *mod* **BetterStorage**.



<p align="center">
  <img src='https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/Backpack.png'>
</p>
<p align="center">Figura 4 - CardboardBackpack em ambiente de jogo</p>



<a name="pull">
### *Pull Request*


Após termos implementado esta nova *feature* no **BetterStorage**, executámos um [*pull request*](https://github.com/copygirl/BetterStorage/pull/321), para que os *developers* principais do projeto possam analisar as mudanças implementadas e que caso achem pertinente esta nova *feature*, a possam adicionar ao *branch* [master](https://github.com/copygirl/BetterStorage), efetuando *merge* do *branch* utilizado pelo grupo, *branch* [submission](https://github.com/VascoUP/BetterStorage/tree/submission), para efetuar a *feature*.


<p align="center">
  <img src='https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/pullFeature.png'>
</p>
<p align="center">Figura 5 - Pull request efetuado pelo grupo</p>


No momento de escrita do presente relatório, o grupo ainda não obteve uma resposta por parte dos *developers* do **BetterStorage**.


<a name="conclusion">
## Conclusão e análise crítica


Com a análise dos resultados obtidos através do **BetterCodeHub**, podemos concluir que apesar do **BetterStorage** só ter obtido aprovação em **6** parâmetros de avaliação, este é um projeto com uma estrutura bem organizada, apesar de ter fragmentos de código pouco simples. Para além disso, o facto de não conter testes unitários torna-o um projeto com uma avaliação "mais baixa", facto este que ocorre devia à natureza "livre" do projeto, apesar que a falta de testes acaba por dificultar um pouco o trabalho dos contribuidores, uma vez que a existência de testes poderia detetar possíveis bugs e ajudá-los a serem solucionados.

Em relação à *feature* implementada, o grupo acha que seguiu o método usado pelos outros *developers* do **BetterStorage**, tendo criado, um novo modo de armazenamento do *mod*, podendo até desta forma haver uma nova *release* do **BetterStorage**, uma vez que este está "parado" já à bastante tempo. A sua implementação foi feita de forma organizada, tendo no entando dois aspetos que ainda podem ser corrigidos, caso a *developer* principal, [copygirl](https://github.com/copygirl), ache que esses pormenores valem a pena serem mudados.
Esses tais "problemas" já falados no tópico relativo à [implementação da *feature*](#impFeature), no entender do grupo são fruto da falta de documentação do código do projeto, pois caso o mesmo estivesse documentado, talvez conseguissemos resolver esses pormenores e assim a *feature* estaria ainda melhor.

O [*pull request*](https://github.com/copygirl/BetterStorage/pull/321) ainda não foi aceite, mas visto que seguimos todas as indicações que a *developer* principal, [copygirl](https://github.com/copygirl), nos deu no início, achámos que a nossa *feature* tem grandes hipóteses de ser aceite e, posteriormente, fazer parte do projeto principal.


<a name="links">
## Links externos


- Processo de desenvolvimento de *software*: 
      https://pt.wikipedia.org/wiki/Processo_de_desenvolvimento_de_software
      
- Manutenção de *software*: 
      https://pt.wikipedia.org/wiki/Manuten%C3%A7%C3%A3o_de_software
      
- Usabilidade: 
      https://pt.wikipedia.org/wiki/Usabilidade
      
- ***BetterCodeHub*** do **BetterStrage**: 
      https://bettercodehub.com/results/VascoUP/BetterStorage


<a name="contributions">
## Contribuições


- Bruno Santos: **25%**
- Sara Fernandes: **25%**
- Vasco Pereira: **25%**
- Vasco Ribeiro: **25%**
  

<a name="idGrupo">
## Identificação do grupo


####Grupo 05, Turma 03:


   - Bruno Santos (up201402962@fe.up.pt)
   - Sara Fernandes (up201405955@fe.up.pt)
   - Vasco Pereira (up201403485@fe.up.pt)
   - Vasco Ribeiro (up201402723@fe.up.pt)
