# Capítulo 1 - código limpo

## Sobre o que se trata

Recentemente comecei a ler o livro “clean code” (”código limpo” em português). Uma das melhores formas de aprender é ensinando. Por isso, gostaria de compartilhar o conhecimento adquirido neste livro com os devs que ainda não leram e ainda registrar meu conhecimento.

O artigo se refere ao primeiro capítulo do livro em que o assunto tratado é a qualidade do código.

Você poderá ver os seguintes assuntos: 
1. [o que é programar](#programarECodigo), 
2. [O que é um código ruim](#codigoRuim), 
3. [O custo de se ter um código ruim](#custo), 
4. [O círculo vicioso do grande replanejamento](#circuloVicioso), 
5. [Por que os códigos bons se tornam ruins](#bomEmRuim), 
6. [O que é um código limpo](#), 
7. [Termos chaves](#termosChaves), 
8. [O que podemos aprender com isso tudo](#conclusao).

## Uma história

Para começar este artigo, gostaria de iniciar fazendo história. Imagine um cirurgião chamado Robert. Ele está indo fazer uma cirurgia em certo paciente. O paciente está muito ansioso para que a cirurgia ocorra logo e exige que Robert nem lave as mãos, pois assim irá começar mais rápido o procedimento. É algo ilógico, certo? O Dr. não cederá de lavar as mãos por conta da pressão do paciente, já que ele é um profissional e sabe mais sobre o risco de infecções e doenças  e estaria em risco seu paciente (além de estar cometendo um crime). 

Guarde essa história, mais tarde farei uma comparação com ela.

Agora vamos começar, de fato, a falar sobre código.

<h2 id="programarECodigo"> O que é programar e o que é código </h2>

Segundo o livro “especificar requisitos detalhadamente de modo que uma máquina posso executá-lo é programar - tal especificação é o código”.

<h2 id="codigoRuim">O que é um código ruim  ?</h2>

Um código ruim é aquele que temos dificuldade de ler, de trabalhar com ele. Aquele que tira nossa produtividade. verdadeiramente uma bagunça. 

O autor define como: “é como se caminhássemos penosamente por um lamaçal de arbustos emaranhados com armadilhas ocultas. Isso é o que fazemos num código ruim.”.

<h2 id="custo">Tá, mas qual o custo de se ter um código ruim ?</h2>

Um código ruim à medida que cresce, vai se tornando pior. Fica difícil de se trabalhar, de entender, rouba toda a produtividade da equipe. 

Fica custoso de se trabalhar e pode até levar uma empresa à falência. Isso faz com que a alta produtividade que se tinha no começa se converta em lentidão quanto mais cresce, esse código sujo. 

Dessa forma, fica inviável de se trabalhar com ele. É aí que entra outro problema: **O círculo vicioso do grande replanejamento**.

<h2 id="circuloVicioso">O círculo vicioso do grande replanejamento</h2>

Como abordado anteriormente, o código se torna inviável de se trabalhar e é aí que começa a bagunça:

1. A empresa contrata mais devs em uma tentativa de aumentar a produtividade daquele código ruim (o que não faz tanto sentido, nove grávidas não fazem um bebê em um mês).
2. Os novos devs não têm o entendimento desse sistema.
3. A pressão aumenta ainda mais sobre eles para que se aumente a produtividade, criando mais e mais confusões - diminuindo ainda mais a produtividade.
4. A equipe se rebela, não conseguem mais trabalhar nesse código fonte e acaba exigindo um replanejamento do projeto.
5. A gerência não quer gastar recursos em uma nova remodelação. A produtividade está péssima e acaba cedendo às exigências dos devs e autoriza o grande replanejamento. 
6. Eles são divididos em duas equipes. Uma com os devs mais brilhantes para fazer o projeto inteiramente novo e acompanhar as mudanças feitas no antigo. Outra com o restante dos devs, que precisam fazer a manutenção do sistema antigo e fazer mudanças necessárias.
7. Torna-se uma corrida: a equipe precisa construir o novo código fazendo o mesmo que o anterior e ainda se manter atualizado com as mudanças feitas no sistema antigo.
8. A corrida pode durar um bom tempo. Quando termina, os membros originais da nova equipe se foram há muito tempo e tudo vira uma zona de novo. Dessa forma, os novos exigem um grande replanejamento…

 
<h2 id="bomEmRuim">Por que os códigos bons se tornam ruins ?</h2>

há diversas razões para isso acontecer, o livro aborda as seguintes:

### Pressão por parte da gerência

Lembra da história que eu te contei no início, sobre o cirurgião Robert e o paciente ? 

Nesse caso vamos fazer um paralelo. O paciente é a gerência, exigindo resultados dentro de uma prazo curto, e o médico são os programadores. Ao escrever o código com pressa, códigos desorganizados são escritos, tornando ainda o sistema em uma bagunça. 

## Deixar pra depois

Podemos deixar para refatorar depois por diversos motivos, seja o primeiro já mencionado, ou cansaço, pressa, tentar ser rápido, etc. 

Por essas razões, muitas vezes fazemos uma bagunça e escolhemos arrumar depois.

O que acontece muitas vezes é vermos o programa confuso funcionar e decidir que uma bagunça que funciona é melhor do que nada. 

Dessa forma, a ação de refatorar muitas vezes acaba ficando no campo das promessas. 

Mas agora que você está lendo este artigo, lembre-se da lei de LeBlanc em que ***Mais tarde é igual a nunca.***

<h2 id="codigoBom">Se já sabemos o que é um código ruim, vamos ver O que é um código limpo.</h2>

No livro essa pauta é levantada e o autor nos mostra algumas falas de alguns dos programadores mais experientes e influentes. 

Uma das falas que mais gostei e que é mais completa é de Ron Jeffries, autor de Extreme programming Installed and Extreme Programming Adventures in C#. 

Ron criou códigos em quase todas as linguagens e máquinas. 

 Sua citação é a Seguinte: 

<blockquote>   
  "Nestes anos recentes, comecei, e quase finalizei, com as regras de Beck sobre código simples, em ordem de prioridade, são: 

- Efetue os testes;
- Sem duplicação de código;
- Expresse todas as ideias do projeto que estão no sistema;
- Minimize o número de entidades, como classes, métodos, funções e outras do tipo.

     Dessas quatro, foco-me mais na duplicação. Quando a mesma coisa é feita repetidas vezes, é sinal de que uma ideia em sua cabeça não está bem representada no código. Tento descobrir o que é e, então, expressar aquela ideia com mais clareza.

     Expressividade para mim são nomes significativos e costume mudar o nome das coisas várias vezes antes de finalizar. Com ferramentas de programação modernas, como o Eclipse, renomear é bastante fácil, e por isso não me incomodo em fazer isso . Entretanto, a expressividade vai além de nomes. Também verifico se um método ou objeto faz mais de uma tarefa. Se for um objeto, provavelmente ele precisará ser dividido em dois ou mais. Se for um método, sempre uso a refatoração do Método de Extração, resultando em um método que expressa mais claramente sua função e em outros métodos que dizem com ela é feita.

     Duplicação e expressividade me levam ao que considero um código limpo, e melhorar um código ruim com apenas esses dois conceitos na mente pode fazer uma grande diferença. Há, porém uma outra coisa da qual estou ciente quando programo, que é um pouco mais difícil de explicar.

     Após anos de trabalho, parece-me que todos os programadores pensam tudo igual. Um exemplo é ‘encontrar coisas numa coleção’. Tenhamos uma base de dados com registros de funcionários ou uma tabela de hash de chaves e valores ou um vetor de itens de algum tipo, geralmente procuramos um item específico naquela coleção. Quando percebo isso, costumo implementar essa função em um método ou classe mais abstrato - o que me proporciona algumas vantagens interessantes. 

     Posso implementar a funcionalidade agora com algo mais simples, digamos uma tabela hash, mas como agora todas as referências àquela busca estão na minha classe ou método abstrato, posso alterar a implementação sempre que desejar. Posso ainda prosseguir rapidamente enquanto preservo a capacidade de alteração futura.

     Além disso, a abstração de coleções geralmente chama minha atenção para o que me realmente está acontecendo, e impede que eu implemente funcionalidades arbitrárias em coleções quando tudo o que eu preciso são simples maneiras de encontrar algo o que desejo.

     Redução de duplicação de código, alta expressividade e criação no início da abstração simples. É isso que torna para mim um código limpo."
  </blockquote>

 
<h2 id="termosChaves">Termos chaves</h2>

Termos chaves para entendermos o que é um bom código são: **sem duplicação, uma tarefa, expressividade e pequenas abstrações.**  

Caso você não saiba como implementar esses pontos no seu código, você pode esperar os próximos artigos que publicarei, pesquisar, ver vídeos ou até mesmo ler o livro e, lógico, praticar bastante.

<h2 id="conclusao">O que podemos aprender com isso tudo ?</h2>

Vimos o que é um código ruim, quais são suas implicações e suas causas. Assim, nós podemos (e devemos) usar esses conhecimentos para evitar fazer códigos ruins, pois sabemos a dor de cabeça que um código mal escrito causa futuramente. 

Além disso, esses conhecimentos adquiridos devem despertar a curiosidade a respeito de quais técnicas e “regras” devemos seguir para, de fato, tornar nosso código mais legível e limpo para nós mesmos e os colegas de profissão.
