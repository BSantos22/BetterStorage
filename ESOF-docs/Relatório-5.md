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


Após analisar o código do **BetterStorage** usando o ***BetterCodeHub**, verificámos que somente **60%** das métricas de avaliação, ou seja **6** em **10** parâmetros, é que obtiveram aprovação.

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

O **BetterStorage**, de facto, possui fragmentos pequenos de código, o que faz com que possam ser mais facilmente compreendidos, utilizados somente para uma certa finalidade, contudo estes não são desenvolvidos de forma simples.

Para além disso, o **BetterStorage** está bem dividido em módulos, com um grande grau de independência, podendo-os isolar mais facilmente. Apesar disso, os componentes arquiteturais não estão equilibradas, o que faz com que haja diferente número de componentes distribuídos pelos diferentes módulos, fazendo com que seja mais complicada a localização de certas porções de código.

Por fim, verificou-se que este projeto tem uma base de código pequena e código que o torna bem estruturado e otimizado, o que melhora a manutenção do mesmo, já que uma base de código menor faz com que seja menor o trabalho ao fazer mudanças estruturais.

De referir ainda, que a métrica referente aos testes automáticos não recebeu aprovação, uma vez que este projeto não contém quaisquer módulos de testes, sendo impossível analisar assim tal métrica.



<p align="center">
  <img src='https://bettercodehub.com/edge/badge/VascoUP/BetterStorage'>
</p>
<p align="center">Figura 2 - Badge do projeto</p>



<a name="feature">
## *Feature*


<a name="idFeature">
### Identificação da *feature*


<a name="impFeature">
### Implementação da *feature*


<a name="pull">
### *Pull Request*


<a name="conclusion">
## Conclusão e análise crítica


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


<a name="idGrupo">
## Identificação do grupo


####Grupo 05, Turma 03:

   - Bruno Santos (up201402962@fe.up.pt)
   - Sara Fernandes (up201405955@fe.up.pt)
   - Vasco Pereira (up201403485@fe.up.pt)
   - Vasco Ribeiro (up201402723@fe.up.pt)
