Уважаемые слушатели, вашему вниманию представляется проект *rustyengine*
Приступим

*rustyengine* являет собой графический движок с возможностью отрисовки 3d сцен в консоли и свободой переопределения поведения по умолчанию. На движке была написана простая игра, конкретней о ней, дабы сохранить некую интригу, будет далее.

Хочется рассказать о некоторых интересных технических решениях.
Во-первых, это оптимизация процесса отправки лучей камеры. Коль скоро угол поворота все равно конечен, было принято решение зафиксировать шаг угла поворота и закешировать пучки лучей камеры для всевозможных ее положений. Таким образом, мы экономим runtime на простой отправке лучей. Пример на слайде, для шага $\frac{\pi}{2}$ имеем 24 положения камеры

Во-вторых, *rustyengine* предоставляет возможность определять для каждого объекта отдельную схему отрисовки, то есть, набор символов и дистанцию видимости. Пример на скриншоте. Можно провести аналогию с разными цветами разных объектов

Движок написан на языке Rust и содержит два интересующих нас модуля:
- `math`
- `engn`

*rustyengine* способствует определению своего поведения через реализацию типажей:
- `AsCollided`- для объектов, видимых на сцене
- `AsGameObject`- для объектов, динамично позиционируемых на сцене
- `AsScene`- для списка сущностей, требующего своего алгоритма отображения, возможно лучше оптимизированного для конкретного случая
- `AsEvent` - для определения игровых событий
- `AsEventSys` - для обработки множества событий

Например, для нового типа системы событий мы реализуем `AsEventSys`, а именно, метод добавления события в систему и метод обработки всех событий. После этого эту систему событий можно использовать в экземпляре `Game`

Пример кода, запускающего игру:
1) читаем файл конфигурации
2) создаем экземпляр сцены
3) создаем систему событий движений камеры, предоставляемую самим движком
4) создаем экземпляр игры и запускаем ее
Это кусочек кода из игры, о которой говорилось ранее. Давайте наконец посмотрим на нее.