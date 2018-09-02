# VSS-Simulator [![GitHub stars](https://img.shields.io/github/contributors/VSS-SDK/VSS-Simulator.svg?style=social&label=Contributors)](https://github.com/VSS-SDK/VSS-Simulator)

[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)][mit]
[![Build Status](https://api.travis-ci.com/VSS-SDK/VSS-Simulator.svg?branch=master)][travis]

O VSS-Simulator é o simulador de partidas de futebol para a categoria IEEE Very Small Size Soccer. O projeto
fornece um mundo 3D feito utilizando a biblioteca [Bullet Physics](http://bulletphysics.org/wordpress/), 
onde os objetos colidem e possuem restrições cinemáticas e dinâmicas. Há também um árbitro que detecta gols
e reposiciona os objetos em campo, fazendo o jogo prosseguir.

* [Enviando comandos](sendcommand.md)
* [Obtendo estados](recvstate.md)
* [Flags de execução](simulatorexeflag.md)
 
## Dimensões do campo

O campo possui 1 metro e 70 centímetros de largura (contando a área de dentro do gol) e 1 metro e 30 centímetros
de profundidade. A origem é em um canto (no canto superior esquerdo se for comparar com o VSS-Viewer). O ponto (0cm, 0cm)
é fora do campo, devido a área do gol ser considerada no plano cartesiano. O centro do campo é no ponto (85cm, 65cm).

## Dimensões dos robôs

Os robôs possuem 8cm x 8cm x 8cm com um shape de um cubo. Atualmente estão sendo reunidos esforços para importar uma malha
de triângulos para os robôs.
 
[travis]: https://travis-ci.com/VSS-SDK/VSS-Simulator
[mit]: https://raw.githubusercontent.com/SIRLab/VSS-Simulator/master/LICENSE.txt