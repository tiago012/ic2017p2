<!--
2º Projeto de Introdução à Computação 2017/2018 (c) by Nuno Fachada

2º Projeto de Introdução à Computação 2017/2018 is licensed under a
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-nc-sa/4.0/>.
-->

# 2º Projeto de Introdução à Computação 2017/2018

> Este enunciado está em construção e não deve ser usado
> como base para o projecto enquanto esta mensagem aqui estiver.

O projecto deve ser realizado em grupos de 2 a 3 alunos. A constituição dos
grupos deve ser comunicada ao docente via Moodle até 27 de dezembro, data a
partir da qual se assume que os alunos não pretendem realizar o projecto na 1ª
época.

## Descrição do problema

Pretende-se que os alunos desenvolvam um jogo/simulador no qual zombies
perseguem e infectam humanos. O jogo desenrola-se numa grelha 2D
toroidal<sup>[1](#fn1)</sup> com dimensões _X_ e _Y_ e vizinhança de
Moore<sup>[2](#fn2)</sup>. Em cada célula da grelha pode estar no máximo um
agente, que pode ser um **zombie** ou um **humano**. No início da simulação
existem _n<sub>z</sub>_ zombies e _n<sub>h</sub>_ humanos, num total de _n =
n<sub>z</sub>_ + _n<sub>h</sub>_ agentes.

O jogo é _turn-based_, e em cada _turn_ (iteração) cada agente pode realizar
uma acção. Os humanos têm disponível apenas uma acção: movimento. Os zombies
podem realizar dois diferentes tipos de acção: 1) movimento; e, 2) infeção de
humanos. O movimento dos agentes pode ser realizado para uma célula vazia numa
vizinhança de Moore de raio 1. A infeção de humanos pode ser realizada por
zombies quando o humano está numa célula adjacente na vizinhança de Moore. A
ordem em que os agentes executam as suas acções em cada _turn_ é
aleatória<sup>[3](#fn3)</sup>, de modo a que nenhum agente em específico
obtenha a vantagem de agir cedo durante todo o jogo.

Os agentes podem ser controlados pelo computador através de uma AI básica, ou
podem ser controlados por um ou mais jogadores. Neste último caso, o jogador
que controla o agente pode decidir o destino do mesmo. Se o agente for um
zombie, a acção de infecção equivale à indicação de movimento para o local onde
está um humano. O zombie não se move, mas o humano converte-se em zombie. Se
o humano era controlado por um jogador, deixa de o ser, e passa a ser
controlado pela AI.

Caso um agente seja controlado pela AI, as suas decisões dependem do tipo de
agente:

* Humano - O humano move-se na direção oposta ao zombie mais próximo.
* Zombie - Caso exista um humano numa célula adjacente, infecta-o. Caso
  contrário, move-se na direção do humano mais próximo.

## Modo de funcionamento

Programa deve aceitar como único parâmetro ficheiro de configuração com o
formato indicado em baixo. Senão for indicado um ficheiro, o programa deve
terminar a execução com uma mensagem de erro para `stderr`, indicando o modo de
uso do comando.

```
in progress
```

Comandos para controlar jogador e visualização.

## Visualização do jogo

Usar código fornecido para a 1ª parte, desenvolver código próprio para a 2ª
parte.

## Primeira parte

* Tamanho do ambiente e número de agentes fixo após compilação: _X_=20, _Y_=20,
_n<sub>z</sub>_=20, _n<sub>h</sub>_=20.
  * Sugestão: usar constantes e ignorar valores lidos do ficheiro de
    configuração.
* Visualização do jogo pode ser feita com código disponibilizado no enunciado.

### Critério de avaliação

Work in progress

### Data de entrega

* 7 de janeiro de 2018

## Segunda parte

* Tamanho do ambiente e número de agentes variável após compilação.
* Documentação com [Doxygen].
* Organização do programa em vários ficheiros com uso de Makefile.
* Visualização do jogo deve ser feita com recurso a uma biblioteca gráfica.
  Algumas sugestões:
  * [g2] - Simples mas limitada.
  * [Ncurses] - ASCII art (texto), ver referência [\[2\]](#ref2).
  * [Allegro5] - Bom meio termo, com bons exemplos em C.
  * [SDL2] - Muito versátil e poderosa, mas poucos exemplos em C.
  * [Raylib] - Muito interessante, mas instalação no Ubuntu não é trivial (ver
    instruções no Wiki da [página no GitHub][Raylib-gh]).

### Critério de avaliação

Work in progress

### Data de entrega

* 21 de janeiro de 2018

## Sugestões para o desenvolvimento do projecto

1. Começar com coisas simples

## Extensões opcionais, trabalho futuro e Global Game Jam

* Melhor AI.
* Melhor integração com biblioteca preferida: [Ncurses], [Allegro5], [SDL2] ou
  [Raylib]. Infelizmente [g2] não é apropriada para jogos "a sério".
* Desenvolvimento do jogo na Global Game Jam.

## Notas

<sup><a name="fn1">1</a></sup> Nota de rodapé sobre toros

<sup><a name="fn2">2</a></sup> Nota de rodapé sobre Moore

<sup><a name="fn3">3</a></sup> Nota de rodapé sobre _shuffling_

## Referências

* <a name="ref1">\[1\]</a> Pereira, A. (2017). C e Algoritmos, 2ª edição. Sílabo.
* <a name="ref2">\[2\]</a> Reagan, P. (2014). [Game Programming in C with the
Ncurses Library](https://www.viget.com/articles/game-programming-in-c-with-the-ncurses-library),
Viget Labs.


## Licenças

Todo o código neste repositório é disponibilizado através da licença [GPLv3].
O enunciado e restante documentação são disponibilizados através da licença
[CC BY-NC-SA 4.0].

## Metadados

* Autor: [Nuno Fachada]
* Curso:  [Licenciatura em Aplicações Multimédia e Videojogos][lamv]
* Instituição: [Universidade Lusófona de Humanidades e Tecnologias][ULHT]



[GPLv3]:https://www.gnu.org/licenses/gpl-3.0.en.html
[CC BY-NC-SA 4.0]:https://creativecommons.org/licenses/by-nc-sa/4.0/
[lamv]:https://www.ulusofona.pt/licenciatura/aplicacoes-multimedia-e-videojogos
[Nuno Fachada]:https://github.com/fakenmc
[ULHT]:https://www.ulusofona.pt/
[aed]:https://fenix.tecnico.ulisboa.pt/disciplinas/AED-2/2009-2010/2-semestre/honestidade-academica
[ist]:https://tecnico.ulisboa.pt/pt/
[Markdown]:https://guides.github.com/features/mastering-markdown/
[GCC]:https://gcc.gnu.org/
[Clang]:https://clang.llvm.org/
[Gedit]:https://wiki.gnome.org/Apps/Gedit
[Geany]:https://www.geany.org/
[Code::Blocks]:http://www.codeblocks.org/
[Atom]:https://atom.io/
[XCode]:https://developer.apple.com/xcode/
[Notepad++]:https://notepad-plus-plus.org/
[Remarkable]:https://remarkableapp.github.io/
[Git]:https://git-scm.com/
[repositório]:https://github.com/VideojogosLusofona/ic2017p1
[GitHub]:https://github.com/
[git-tutorial]:https://try.github.io/levels/1/challenges/1
[Moodle]:https://secure.grupolusofona.pt/ulht/moodle/
[GitLab]:https://gitlab.com/
[BitBucket]:https://bitbucket.org/
[NotABug]:https://notabug.org/
[StackEdit]:https://stackedit.io/editor
[(GitHub-Flavored) Markdown Editor]:https://jbt.github.io/markdown-editor/
[Doxygen]:http://www.stack.nl/~dimitri/doxygen/
[Ncurses]:https://www.gnu.org/software/ncurses/ncurses.html
[g2]:http://www.ncbr.muni.cz/~martinp/g2/index.html
[Allegro5]:http://liballeg.org/
[SDL2]:https://www.libsdl.org/
[raylib]:http://www.raylib.com/
[raylib-gh]:https://github.com/raysan5/raylib
