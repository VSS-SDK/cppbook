# Visão Geral [![GitHub stars](https://img.shields.io/github/stars/VSS-SDK/VSS-SDK.svg?style=social&label=Stars)](https://github.com/VSS-SDK/VSS-SDK)

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)][gpl3]

O VSS-SDK é um projeto opensource que auxilia equipes na construção de times de futebol de robôs. 
O SDK possui foco na categoria IEEE Very Small Size Soccer, presente na Competição Brasileira de Robótica (CBR) 
e na Competição Latino-Americana de Robótica (LARC). 

* [Instalação](install.md)
* [Utilização](use.md)
* [Desenvolvimento](dev.md)

![viewer](https://raw.githubusercontent.com/VSS-SDK/assets/master/images/sdk.png)
VSS-Viewer plotando estados do VSS-Simulator e informaçoes de debug de uma estratégia.

O SDK é formado por 5 projetos e alguns exemplos. São esses: 

* VSS-Vision - Sistema de visão computacional.
* [VSS-Simulator](vsssimulator.md) - Simulador de partidas de futebol.
* [VSS-Viewer](vsscore.md) - Visualizador de estados e debug.
* [VSS-Joystick](vssjoystick.md) - Programa de controle de robôs via joysticks usb/bluetooth.
* [VSS-Core](vsscore.md) - Biblioteca com interfaces de comunicação, domínio, métodos úteis e etc  . 
* [VSS-Samples](samples.md) - Exemplos de estratégias

São utilizados tecnologias que possibilitam a construção de estratégias em várias linguagens. Atualmente, 
existem dois exemplos de como realizar a comunicação com os projetos, um em C++ e outro em Rust. 
No futuro serão adicionados mais exemplos.

Atualmente são suportados somente distribuições Linux, como: Ubuntu 14, Ubuntu 16, Ubuntu 18, Linux Mint 18
e Debian 9.

[gpl3]: http://www.gnu.org/licenses/gpl-3.0/
[travis]: https://travis-ci.com/VSS-SDK/VSS-SDK