﻿# Оценочная функция и minimax

Это репозиторий с заготовкой бота для игры 
[WondevWoman](https://www.codingame.com/multiplayer/bot-programming/wondev-woman).

![WondevWoman-logo](logo.png)

В этом блоке задач мы рассмотрим несколько базовых концепций проектирования игровых ИИ.

Но для начала вам нужно познакомиться с правилами игры и написать элементарного бота прямо в браузере.
Пройдите несколько первых лиг, чтобы открыть полные правила игры. 

### [Вперёд!](https://www.codingame.com/multiplayer/bot-programming/wondev-woman)

После того, как познакомитесь с игрой, склонируйте этот репозиторий. 
В нём мы проделали большую часть технической работы запрограммировали ввод/вывод, а также правила игры. 
Обязательно почитайте уже написанный код, ведь если вы будете писать бота с нуля для другой игры, всё это вам придётся сделать самим.

Особенный интерес представляет код симуляции игры (в просторечье «сима») в классе State.cs. 
Это класс, который хранит состояние игры, а в методах запрограммированы правила игры.

Применение любых продвинутых техник программирования ИИ возможно только при наличии симуляции,
и чем точнее она повторяет оригинальные правила, тем эффективнее бот. 
Часто исправление неточности симуляции улучшает игру бота сильнее, чем любые другие «умные» улучшения.

Изучите симуляцию, это поможет лучше разбираться в происходящем, когда вам придется её использовать. 

## Задачи

1. Задача [Оценочная функция](EvaluationFunction.md) 
(в простонародье «оценка»). После выполнения этой задачи у вас будет работоспособный, неплохо играющий бот.

2. Задача [Minimax и αβ-отсечение](Minimax.md). Применив эту технику можно уверенно войти в топ-100 золотой лиги, что очень неплохой результат.

Ещё выше можно забраться только доработав алгоритм детекции позиции соперника.
Это одна из ключевых составляющей, а в стартовом репозитории реализован лишь предельно простой алгоритм. 
Как его можно улучшить хорошо написал игрок Agade [в своём отчёте](https://github.com/Agade09/Agade-Wondev-Woman-Postmortem/blob/master/Agade_WW_Postmortem.md). 
Там же можно почерпнуть и другие полезные идеи.

После детекции соперника, имеет смысл продолжать ускорять minimax, либо за счет более умного упорядочивания ходов, 
чтобы отсечение сильнее уменьшало перебор, либо за счёт профилирования и оптимизаций, чтобы перебор работал быстрее.

Каждое изменение стоит тестировать, сравнивая скорость работы, размер дерева поиска и корректность 
на одинаковых тестовых входах до и после изменения.