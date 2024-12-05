# Portal Estelar 3D

### [Link para o WebAssembly](helloworld.html)

<br>

Pedro Antunes Negrão - 21086916<br>
Renato dos Santos - 11202021103

UFABC - Computação Gráfica - 2024.3<br>
Prof. Celso S. Kurashima

## Objetivo

Este projeto tem como objetivo aplicar conceitos de projeções, movimentações de objetos, câmera lookAt e transformações no OpenGL. Ele foi baseado no projeto _starfield_ da disciplina e consiste em um jogo onde o usuário controla uma nave espacial utilizando as setas do teclado (cima, baixo, direita e esquerda) e precisa passar por Portais Estelares.

## Técnicas implementadas

Para este projeto foram implementadas diversas técnicas ensinadas no decorrer do curso até então, como:

- Utilização de modelos 3D .obj (foram utilizadas 2 modelos, um torus representando os portais e uma nave espacial, ambos obtidos no site Cults3d.com);
- Câmera LookAt para construir a visão da cena usando o quadro da câmera;
- Projeção perspectiva para simular a percepção do mundo real, onde a nave se locomove em direção aos portais;
- Movimentação da nave utilizando as setas do teclado (cima, baixo, direita e esquerda) com limitação, para fazer com que a nave não saia do campo de visão da câmera;
- Utilização de matrizes de transformações para modelarmos os objetos conforme necessário, como translação, escala e rotação. Por exemplo, foi necessário rotacionar o modelo da nave espacial porque ela veio em pé no arquivo .obj;

## Próximos Passos

Para a última entrega, será implementado uma fonte de iluminação (simulando o Sol) para aplicar os conceitos de luzes e sombras, além de também implementar as texturas nos objetos, tanto na nave quanto nos portais.