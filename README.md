#Utilizando Branchs

##Neste "capitulo" veremos alguns comandos para utilizarmos branchs, como acontece no dia a dia em uma empresa de tecnologia.

------------------------------------------------------------------------------------------------------------------------------------------

###O que são branchs?

Imagine uma árvore, o tronco (versão mais sólida) e seus galhos (ramificações) contem as mesmas propriedades da arvore, porém os seus galhos se modificam mais facilmente que o seu tronco, que demora mais para uma mudança percepitível.

Quando criamos um projeto e clonamos ou iniciamos o git em nosso workspace um branch "master" é criado por default, imagine que esse é o tronco da árvore e contém o nosso projeto.
Agora, imagine que nossos programadores vão trabalhar em outras frentes desse projeto, seja alguma melhoria ou nova funcionalidade.
O que seria bagunçado se todos os programadores utilizassem a versão estável que está em funcionamento na nossa master e testassem todos de uma vez...
Então, seria mais prático que utilizassemos "cópias" do projeto, mas que fossem "filhas" ou seja, dependentes do nosso master ( o tronco da arvore, lembra? ).
Um branch, contem exatamente o que existe dentro do master (sua origem) porém, podemos modifica-lo avontade e depois, no final dos testes basta fazer um merge com o master (se ele é dependente da master, ao fazer o merge, estamos pegando tudo que foi modificado e está testado e estável e colocando junto ao master que é nossa versão principal!

------------------------------------------------------------------------------------------------------------------------------------------
###Como utilizar os branchs?

Depois de entendermos que ao criar nossos repositórios estamos na nossa default (master) e que vamos criar os branchs a partir dela, basta utilizar o comando de criação:

**git branch NomeDaBranch**

Assim, tudo o que está na nossa master estará também contido na nossa branch nova!
Para verificar se tudo deu certo, basta utilizarmos o comando:

**git branch**

E todas as branchs serão listadas, note que teremos um asterisco na branch master, isso significa que estamos na branch master e não na branch nova que criamos.

**lembre-se, criar uma branch não significa que o git ira mudar automaticamente para ela**

Então como começamos a trabalhar na nossa branch nova?
Para mudarmos de branch, utilizamos o comando checkout

**git checkout NomeDaBranch**

Novamente, utilize o **git branch**, verá o asterisco agora na branch nova!

------------------------------------------------------------------------------------------------------------------------------------------
###Commitar na branch e git merge

Após trabalharmos na nossa branch nova, vamos querer "subir" as atualizações para o nosso github certo?

Basta utilizarmos o add ., commit -m e push normalmente, com apenas uma diferença...

Para o push, vamos utilizar o:

**git push origin**(remote que estamos utilizando) **NomeDaBranch**

Verifique se deu certo, ao finalizarmos os trabalhos e subirmos para o github, vamos dar um merge na master para que fique tudo emparelhado (master e branch), para isso, utilizamos o comando:

**git merge NomeDaBranch**


As branchs serão "mergeadas"


------------------------------------------------------------------------------------------------------------------------------------------

###Git Rebase

Com o git rebase, nos equalizamos as branchs, colocando-as no mesmo nível

O rebase transporta os commits de uma branch atualizada para uma branch desatualizada, onde o conteúdo da branch desatualizada ou já está na branch atualizada ou não pode ser mergeado ainda.


Para isso utlizamos o comando:

**git rebase master** (a partir da branch que vc quer nivelar)

------------------------------------------------------------------------------------------------------------------------------------------

###Verificando se tudo está no mesmo nível.

O github conta com uma ajuda gráfica que nos mostra em qual nível estão as coisas, para verificarmos isso:

Entrar no repositório no github > Graphs > network
