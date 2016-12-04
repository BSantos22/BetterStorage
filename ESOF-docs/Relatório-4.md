# Relatório 4



## Índice


1. [Introdução](#introduction)
2. [Grau de Testabilidade](#testability)
  1. [Contrabilidade](#controllability)
  2. [Observabilidade](#observability)
  3. [Isolabilidade](#isolateability)
  4. [Separação de preocupações](#preocupations)
  5. [Percetibilidade](#understand)
  6. [Heterogeneidade](#heterogeneidade)
3. [Estatísticas de Teste](#statistics)
4. [*Bug*](#bugs)
  1. [Identificação do *bug* a tratar](#bugid)
  2. [Resolução do *bug*](#bugres)
  3. [*Pull Request*](#pull)
5. [Conclusão](#conclusion)
6. [Links Externos](#links)
7. [Contribuições](#contribuitions)
8. [Identificação do Grupo](#idgrupe)


<a name="introduction">
## Introdução


Este relatório irá-se focar na **verificação** e **validação** do *software* desenvolvido no projeto **BetterStorage**.

O processo de **verificação** e **validação** permite confirmar que o *software* desenvolvido cumpre com todas as especificações e ideais que o próprio cliente requeriu. Estes dois componentes interligam-se, como se pode ver de seguida:


<p align="center">
  <img src="https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/VerificationValidation.jpg">
</p>

<p align="center">
  Figura 1 - Diagrama referente à verificação e validação de software
</p>


O componente de **verificação** tenta garantir, principalmente, através de análises, que os produtos do trabalho e o próprio trabalho final são "bem construídos", isto é, que estão em conformidade com os seus requisitos especificados.

Já o componente de **validação** tenta garantir, através de testes, que o produto final cumpre com a sua intenção. Este pode, igualmente, ser aplicado a produtos intermédios, do respetivo trabalho, como uma espécie de previsão relativa a como é que o produto final irá satisfazer as necessidades do usuário.


<p align="center">
  <img src="https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/VerificationValidation2.png">
</p>

<p align="center">
  Figura 2 - Esquema de interligação entre a verificação e validação de software
</p>


O **BetterStorage**, por ser um projeto "livre" onde qualquer um pode ser um contribuidor, podendo participar no desenvolvimento do mesmo, sofre de alguns problemas de testabilidade. Este não contém um módulo relativo a testes, uma vez que tanto a *developer* principal, [copygirl](http://github.com/copygirl) como os restantes contribuidores preferiram criar código e testá-lo manualmente, jogando o jogo *Minecraft*, verificando aí a possível existência de erros.

Apesar de não existirem testes no **BetterStorage**, decidimos supôr como seriam os resultados obtidos em relação ao *grau de testabilidade* e às suas respetivas secções.

Neste relatório, portanto,  explorar-se-á o **grau de testabilidade** do *software*, analisando a **controlabilidade** dos componentes, a **observabilidade** e **isolabilidade** dos mesmos, assim como o **grau de separação de preocupações**, de **percetibilidade** e **heterogeneidade** das tecnologias utilizadas.

Para além disso, vão ser ainda apresentadas algumas estatísticas pertinentes, relacionadas com a verificação e validação do *software*.
Por fim, será apresentado o *bug* selecionado pelo grupo, para ser resolvido, assim como todos os passos efetuados para a sua resolução.


<a name="testability">
## Grau de Testabilidade


A análise referente ao **grau de testabilidade** de um projeto é bastante importante, visto que assim é verificado se os testes têm uma complexidade que permite que todos os componentes envolvidos no *software* sejam testados. Caso o **grau de testabilidade** de um componente seja elevado, significa que é mais fácil encontrar *bugs* no mesmo, podendo-os corrigir com maior facilidade, igualmente.

O **BetterStorage**, como já referido, não contém nenhum tipo de testes, o que faz com que uma vez que o grupo está a supôr certos resultados que poderiam ocorrer caso existisse um  módulo de testes, não se possa analisar o **grau de testabilidade** do projeto de forma concreta e 100% correta. Para tal, iremos identificar e explicar o que ocorre em cada secção do **grau de testabilidade**, referindo o que devia de acontecer caso o **BetterStorage** tivesse testes unitários.

O **grau de testabilidade**, como é indicado, é dividido em diferentes secções, como:
- Controlabilidade
- Observabilidade
- Isolabilidade
- Separação de preocupações
- Compreensibilidade
-	Heterogeneidade


<a name="controllability">
### Contrabilidade

A **controlabilidade** é uma fase em que é possível controlar o estado do componente que irá ser testado (*CUT - Component Under Test*) em conformidade com o teste respetivo.

Uma vez que o **BetterStorage** não contém testes unitários, não podemos falar concretamente dos módulos existentes e como estes se comportariam ao serem testados. 

Caso este projeto tivesse testes unitários, provavelmente, a **controlabilidade** dos componentes do módulo principal do **BetterStorge** seria reduzida, uma vez que estes dependem de outros módulos. Já a **controlabilidade** dentro de cada módulo seria maior, visto que a maior partes dos componentes de cada módulo interagem com os restantes componentes do módulo respetivo. 

Deste modo, a **controlabilidade** mais elevada dos componentes dos módulos torna mais fácil a execução de testes existentes, em relação a alguns componentes do módulo principal. Contudo, componentes mais "interiores" do módulo principal poderão apresentar a mesma facilidade (quando considerada apenas a **controlabilidade**), visto que possuem interações mais limitadas e funcionalidades mais concentradas.

Podemos, assim, afirmar que quanto maior for a profundidade do componente, em relação à sua posição no código, maior será a **controlabilidade** do mesmo.

<a name="observability">
### Observabilidade

A **observabilidade** é a capacidade de analisando os resultados dos testes, conseguir interpretar os testes e perceber a origem de diversas falhas possíveis.

Uma vez que o **BetterStorage** não contém testes, torna-se difícil analisar a **observabilidade** que teriam os mesmos, pois esta depende também da técnica usada para implementar os testes.

No entanto, caso se implementassem testes unitários seria útil ter informações sobre *Code Coverage* (tamanho da cobertura dos testes), *FindBugs* (zonas do código que pode originar bugs), e *Checkstyle* (se usa sempre o mesmo estilo de código em todo o sítio). Principalmente, com estes 3 tipos de testes, a **observabilidade** seria muito boa e de fácil interpretação pois os resultados dos testes, assim divididos, permitiriam uma melhor perceção das falhas do código.


<a name="isolateability">
### Isolabilidade

Ao falar em **isolabilidade** de um componente, estamos a falar da forma como este pode ser testado de forma isolada, dependendo, contudo, da forma que ele se relaciona com outros módulos ou da sua relação com os mesmos. Resumidamente, é a capacidade de testarmos fragmentos do código que em caso de falha nos permitem identificar logo o problema. Um código onde haja muitas dependências de um módulo por outro, será mais difícil de testar, uma vez que, testando um dos módulos ele pode estar a falhar por caso do outro módulo ter algo errado, e estar, inteiramente correto o código do próprio modulo. Assim,  podemos afirmar que, a **isolabilidade** de módulos secundários seria maior que a isolabilidade dos módulos princiapais, pois os módulos principais dependem de mais funções auxiliares do que os secúndarios, sendo mais difíceis de isolar.

O nosso projeto, **BetterStorage**, não tem testes unitários o que torna difícil abordar a **isolabilidade** do mesmo. Deste modo, determinar um grau geral de **isolabilidade** do código torna-se impossível, sabendo apenas que esta está relacionada com a **controlabilidade** do código, pois este se relaciona também com estado do componente a ser testado.


<a name="preocupations">
### Separação de Preocupações


**Separação de preocupações**  é a fase em que o componente a ser testado tem responsabilidade única, clara e objetiva.

A separação de preocupações / responsabilidades entre módulos, no **BetterStorage** está muito bem definida, como já foi referido no [relatório anterior](https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/Relatório-3.md). Os responsáveis pelo **BetterStorage* optaram por dividir o código por diferentes *packages*, tentando estruturar o mesmo de forma simples, tentando evitar que haja repetição ou criação de código sem qualquer utilidade. Consuante a importância e a complexidade de cada fragmento de código, maior ou mais complexo será o *package* que o contém.

Assim, verifica-se que este projeto tem uma boa **separação de preocupações**, o que faria com que cada componente fosse testado com um certo intuito, caso existissem testes unitários no **BetterStorage**.


<a name="understand">
### Percetibilidade


A **percetibilidade** é a fase onde o componente a ser testado se encontra bem documentado e auto-explicativo.

Como já indicado no [relatório anterior](https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/Relat%C3%B3rio-3.md), praticamente todos os módulos do **BetterStorage** não se encontram documentados ou detêm quaiquer tipos de ficheiros auto-explicativos havendo, somente, um número escasso de funções com algumas explicações.

Isto torna muito complicada a perceção e compreensão do código por parte de contribuidores externos fazendo com que, caso houvessem testes unitários, fosse mais difícil a resolução de problemas que poderiam ocorrer, uma vez que um possível contribuidor podia não compreender o que certa função estaria a fazer.


<a name="heterogeinidade">
### Heterogeneidade

<a name="statistics">
## Estatísticas de Teste


Visto que, como já referido anteriormente, o **BetterStorage** não contem um módulo com testes unitários, é impossível analisar a percentagem de **cobertura** dos mesmos, assim como tudo o que poderá advir destes.

Apesar de não se conseguir estimar percentagens relativas aos testes, através do site [codacy](https://www.codacy.com), conseguimos perceber um pouco mais acerca do **BetterStorage**, tendo obtido diversas informações relativas ao **estilo de código**, **compatibilidade** do mesmo, **possibilidade de ocorrência de erros**, ***performance***, **segurança** e **percentagem de código não usado**.

Ao todo encontraram-se **203** ***issues*** relativamente ao código desenvolvido no **BetterStorage**.


<p align="center">
  <img src="https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/issuesCodacy.png">
</p>

<p align="center">
  Figura 3 - Issues reportados pelo site codacy
</p>


As ***issues*** reportadas, como se pode ver através da figura anterior, têm uma distribuição percentual diferente. Essa distribuição pode ser vista em:


<p align="center">
  <img src="https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/codacy.png">
</p>

<p align="center">
  Figura 4 - Distribuição percentual das issues
</p>


Em relação ao **estilo do código**, com uma percentagem de **95%**, pode-se concluir que o **BetterStorage** está implementado com um bom estilo de desenvolvimento, onde os **5%** que faltam para atingir a “perfeição” se referem a métodos vazios, disposição da inicialização de variáveis no código e a métodos com uma definição demasiado longa. Este pequenos “erros” de estilo estão distribuídos uniformemente pelo **BetterStorage**, não havendo um módulo ou componente onde haja uma incidência mais acentuada dos mesmos.

Relativamente à **compatibilidade do código**, com uma percentagem de **100%**, unicamente se pode concluir que é um projeto perfeitamente compatível com a linguagem de programação utilizada (linguagem *Java*).

No caso da **possibilidade de ocorrência de erros** a percentagem marcada é de **39%**, o que significa que existe uma possibilidade de **61%** de ocorrência de erros. Todos os problemas apontados como possíveis potencializadores de erros são pequenos pormenores, cuja maior incidência recai sobre o uso do operador de comparação de igualdade (**'=='**) em vez da função **equals()**, para comparar referências a objetos, ou sobre a reatribuição de parâmetros.

Tanto em termos de ***performance*** como de **segurança**, através da análise da percentagem obtida, que em ambos os casos é de **100%**, chegou-se à conclusão que o **BetterStorage** é executado da melhor forma possível, tendo código perfeitamente seguro.

Por fim, em relação à percentagem de **código não utilizado**, pode-se verificar que esta é de **8%**, uma vez que o [codacy do projeto](https://www.codacy.com/app/saracouto1318/BetterStorage/dashboard) marca **92%** de código usado. Isto significa que praticamente todo o código desenvolvido para o **BetterStorage** é utilizado, o que faz com que se conclua que por norma ao haver contribuições para o mesmo estas são assertivas e realizáveis, uma vez que contribuem verdadeiramente para o projeto.

Assim, o projeto é classificado pelo [codacy](https://www.codacy.com) como um projeto de **nível B**, o que significa que é um bom projeto, a nível estrutural e de desenvolvimento de código,  com algumas falhas, falhas estas que podem causar erros futuros, mas com um peso percentual, avaliando no geral, um pouco reduzido.


<p align="center">
  <img src="https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/certification.png">
</p>

<p align="center">
  Figura 5 - Certificação do projeto
</p>


<a name="bugs">
## *Bug*


Um ***bug*** consiste num erro relativo ao funcionamento de um *software*, consistindo numa falha lógica de um programa, podendo causar comportamentos inesperados, sendo causados por erros no prórpio código-fonte, na maior parte das vezes.


<a name="bugid">
### Identificação do *bug* a tratar


O ***bug*** selecionado pelo grupo estava presente na lista de [*issues*](https://github.com/copygirl/BetterStorage/issues) do repositório do **BetterStorage**. Este era a *issue* número **316**, sendo uma das *issues* mais recentes no projeto, com data de **11 de junho de 2016**, tendo sido colocada por um dos contribuidores externos ao projeto, [Wasthereonce](https://github.com/Wasthereonce).


<p align="center">
  <img src="https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/bug.png">
</p>

<p align="center">
  Figura 6 - Bug escolhido pelo grupo
</p>


Como a própria descrição do ***bug***, assinalado a cima, indicada este recaía no facto de quando se colocava um presente por cima de um outro já existente, o presente superior era destruído, terminando o programa com um [relatório de erros](http://pastebin.com/JVxtDXhV).

A *developer* principal do projeto, [copygirl](http://github.com/copygirl), rapidamente colocou uma explicação para a ocorrência do mesmo, aproveitando para referir os locais no código desenvolvido onde poderiam estar as ocorrências que estariam a provocar tal problema. A explicação dada pela [copygirl](http://github.com/copygirl) é citada de seguida:

> Probably something with these [this](https://github.com/copygirl/BetterStorage/blob/master/src/main/java/net/mcft/copy/betterstorage/tile/entity/TileEntityCardboardBox.java#L29) and [that](https://github.com/copygirl/BetterStorage/blob/master/src/main/java/net/mcft/copy/betterstorage/tile/entity/TileEntityPresent.java#L51). If none of the three **if**s run, there won't be an NBT tag on the dropped item, causing **compound** to be null.
> Since I'm not touching modding anymore, I can't fix this.
> Can be avoided by setting **cardboardBoxUses** to something greater than **0**.


Mesmo havendo uma explicação bastante sucinta e esclarecedora, o *bug* não chegou a ser resolvido na altura, tendo sido agora resolvido pelo grupo.


<a name="bugres">
### Resolução do *bug*


Apesar da *developer* principal, [copygirl](http://github.com/copygirl), ter explicado bastante bem quais as possibilidades de código que poderiam estar a causar aquele *bug*, o grupo não consegiu descobrir a sua origem exatamente.

Assim, seguimos os passos que a mesma indicou, tendo implementando uma verificação que caso **compound** seja *null* o programa faz um *return* vazio, evitando que este termine abruptamente quando se coloca um presente por cima de um presente já existente.

Para além desta resolução, o grupo tentou também corrigir outros potenciais problemas, apontados pelo [codacy](https://www.codacy.com/app/saracouto1318/BetterStorage/dashboard), de forma a que fosse minimizado o risco de ocorrência de possíveis *bugs* futuros.

<a name="pull">
### *Pull Request*


Após se ter tentado resolver o problema, foi executado um [*pull request*](https://github.com/copygirl/BetterStorage/pull/319), para que os *developers* principais do **BetterStorage** possam analisar as mudanças implementadas e caso estas sejam vantajosas para o mesmo possa ser feito *merge* do *branch* utilizado, [Bug_Fixes](https://github.com/VascoUP/BetterStorage/tree/Bug_Fixes), para corrigir o *bug* escolhido, de forma a que depois esse código faça parte do *branch* [master](https://github.com/copygirl/BetterStorage) do projeto.


<p align="center">
  <img src="https://github.com/VascoUP/BetterStorage/blob/master/ESOF-docs/resources/pullRequest.png">
</p>

<p align="center">
  Figura 7 - Pull request executado pelo grupo
</p>


Como o [*pull request*](https://github.com/copygirl/BetterStorage/pull/319) foi executado no dia de entrega do presente relatório, o grupo ainda não obteve uma resposta em relação ao seu pedido, não sabendo ainda se a sua resolução foi será aceite.


<a name="conclusion">
## Conclusão

<a name="links">
## Links Externos


  - **Verificação e validação de** ***software***: 
  
  
     - http://testenext.blogspot.pt/2012/10/teste-de-software.html
      
     - http://www.lbd.dcc.ufmg.br/colecoes/ihc/2000/0002.pdf
      
     - https://moodle.up.pt/pluginfile.php/84648/mod_resource/content/1/ESOF-VV.pdf
      
  
  - **Codacy**: https://www.codacy.com
  
  
  - **Codacy do BetterStorage**: https://www.codacy.com/app/saracouto1318/BetterStorage/dashboard
  
  
  - ***Bug***: https://pt.wikipedia.org/wiki/Bug

<a name="contribuitions">
## Contribuições

<a name="idgrupe">
## Identificação do Grupo


####Grupo 05, Turma 03:

   - Bruno Santos (up201402962@fe.up.pt)
   - Sara Fernandes (up201405955@fe.up.pt)
   - Vasco Pereira (up201403485@fe.up.pt)
   - Vasco Ribeiro (up201402723@fe.up.pt)
