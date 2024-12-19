# (2) Portal Estelar 3D Texturizado - (19/12/24)

### [Link para o WebAssembly](helloworld.html)

<br>

Pedro Antunes Negrão - 21086916<br>
Renato dos Santos - 11202021103

UFABC - Computação Gráfica - 2024.3<br>
Prof. Celso S. Kurashima

## Introdução

Este projeto tem como objetivo aplicar conceitos de projeções, movimentações de objetos, câmera lookAt e transformações no OpenGL, além de aplicar iluminação e texturas. Ele foi baseado no projeto _starfield_ da disciplina e consiste em um jogo onde o usuário controla uma nave espacial utilizando as setas do teclado (cima, baixo, direita e esquerda) e precisa passar por Portais Estelares. A ideia do projeto é permitir que o jogador controle a nave espacial e tente fazer a nave passar por entre os portais, sendo que esses portais se aproximam da tela (eixo Z) de forma constante e se movimentam na horizontal (eixo X) utilizando uma função seno, para aumentar a dificuldade do jogador.


## Guia de Utilização

Para movimentar a nave espacial é preciso utilizar as setas do teclado, sendo elas:

- Seta para cima movimenta a nave no eixo Y positivo;
- Seta para baixo movimenta a nave no eixo Y negativo;
- Seta para esquerda movimenta a nave no eixo X negativo;
- Seta para direita movimenta a nave no eixo X positivo;

Além disso, é possível controlar a nave na direção Z, simulando a aceleração ou a desaceleração dela. Para isso, é necessário segurar a barra de espaço e segurar a seta para cima para acelerar (andar na direção do eixo Z negativo) ou segurar a seta para baixo para desacelerar (andar na direção do eixo Z positivo).


## Projeto e Desenvolvimento

Para desenvolver este projeto foi utilizado dois arquivos .obj para renderizar os objetos no cenário. Um deles é o torus.obj que é o arquivo utilizado para renderizar os portais estelares. Esse objeto é um torus, também conhecido como um _donut_, que é um anel com volume. O outro objeto utilizado foi o ship.obj, que é uma nave espacial em 3D. Ambos esses arquivos foram obtidos no site Cults3d e estão salvos na pasta /assets.

A lógica de interação com a nave espacial está descrita no método OnEvent() do arquivo window.cpp. Nesse método foi mapeado as teclas de setas do teclado, permitindo que o usuário interaja com a aplicação, fazendo que com a nave seja movimentada nos 3 eixos do cenário: horizontal (eixo X), vertical (eixo Y) e profundidade (eixo Z).

Para implementação da lógica da animação dos portais, foi desenvolvido o algoritmo dentro do método onUpdate() do arquivo window.cpp. Ou seja, a cada frame de atualização os portais são renderizados de forma que a sua posição seja alterada, modificando os eixos X e Z principalmente. É calculado um offSet para o eixo X, permitindo que ele tenha uma movimentação suave e alternando o sentido da direção, fazendo-o movimentar para a esquerda e para a direita em um loop.

Já para a iluminação foi implementado o modelo de Phong usando sombreamento de Phong, e para isso foi necessário implementar o fragment shader e o vertex shader de Phong, ambos implementados nos arquivos phong.vert e phong.frag dentro da pasta /assets. Foi escolhido esse modelo porque não havia muito diferença ao tentar aplicar o modelo Blinn-Phong, dado que os objetos estão distantes da câmera e não era possível observar o alongamento do brilho especular.

Por fim, para aplicar a texturização nos objetos existentes foi necessário utilizar o mapeamento triplanar, já que esses arquivos .obj foram obtidos de um site de impressão 3D e não havia um mapeamento UV unwrap dentro deles. 


## Resultados e Análises

Diante do projeto desenvolvido, é possível afirmar que foi aplicado com êxito a utilização das técnicas apresentadas ao longo da disciplina utilizando OpenGL, como utilização de modelos 3D, interatividade do usuário, animações de elementos na tela, aplicação dos coneitos sobre iluminação e reflexão da luz nos objetos e texturização dos mesmos. 


## Conclusões

Concluí-se que o desenvolvimento dos 3 projetos no decorrer na disciplina permitiu uma aprendizagem sobre os conceitos computacionais sobre computação gráfica, indo desde modelagem 2D utilizando malha triangular até texturização e iluminação de objetos 3D. Foi uma disciplina desafiadora por conta da complexidade da teoria da matéria, porém foi possível aplicar esses conceitos conforme o avanço do desenvolvimento dos projetos, começando pelos projetos mais simples e finalizando com este projeto em questão, onde foi implementado todos os conceitos da disciplina.

## Referências

[https://hbatagelo.github.io/cg/](https://hbatagelo.github.io/cg/)

[https://cults3d.com/en/3d-model/game/torus-3d-model-beatinstar](https://cults3d.com/en/3d-model/game/torus-3d-model-beatinstar)

[https://cults3d.com/en/3d-model/game/spaceship-blender-test](https://cults3d.com/en/3d-model/game/spaceship-blender-test)


