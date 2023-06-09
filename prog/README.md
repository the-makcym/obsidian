### Прямая
Прямая на расстоянии $\rho$ от начала координат, отрезок нормали к которой из начала координат составляет с положительным направлением $Ox$ угол $\phi$ (против часовой стрелки), задается
$$x \cos{\phi} + y \sin{\phi} - \rho = 0$$
или, параметрически
$$
\begin{cases}
x = \rho \cos{\phi} - t \sin{\phi} \\
y = \rho \sin{\phi} + t \cos{\phi}
\end{cases}
$$

### Преобразование Радона

Пусть все преобразования происходят в квадрате стороны $a$ с центром в начале координат
Тогда расстояние от начала координат до прямой $\rho \in [-\sqrt2 a, \sqrt2 a]$

Если ограничиться кругом радиуса $a$ в начале координат, то $\rho \in [-a, a]$

Благодаря тому, что величина $\rho$, условно имеющая геометрический смысл расстояния, может быть отрицательной, угол между $Ox^+$ и нормалью есть $\phi \in [0, \pi)$ 

Имея **частоту дискретизации ```NRHO``` и ```NPHI```** множество всех прямых ограничивается множеством прямых, для которых
$$
\rho = a \cdot \frac{i}{N_\rho} \;,\; 
i \in [-N_\rho, N_\rho] \;\cap\; \mathbb{Z}
$$
$$
\phi = \pi \cdot \frac{j}{N_\phi} \;,\;
j \in [0, N_\phi) \;\cap\; \mathbb{Z}
$$

### Обращение преобразования Радона

Множество прямых, удаленных от данной точки $(\xi, \eta)$ на расстояние $r$, задается как:
$$
x \cos\phi + y \sin\phi - (\rho(\xi, \eta, \phi) + r) = 0 \;,\; \phi \in [0, \pi)
$$

---

Преобразование Радона используется для получения проекций объекта в разных направлениях. Свертка используется для вычисления преобразования Радона, а обратная проекция используется для обратного преобразования Радона, чтобы восстановить оригинальный объект.

Алгоритм свертки:

1.  Задать угол наблюдения (направление проекции).
2.  Для каждого угла наблюдения, произвести луч, проходящий через каждый пиксель объекта.
3.  Вычислить интенсивность проекции, складывая значения пикселей, которые пересекает луч, после чего результат сохраняется в соответствующей матрице проекций.

Алгоритм обратной проекции:

1.  Задать угол наблюдения (направление проекции).
2.  Для каждого угла наблюдения, произвести луч, проходящий через каждый пиксель в матрице проекций.
3.  Для каждого пикселя, через который проходит луч, прибавить его значение к соответствующему пикселю в восстановленном объекте.
4.  Повторить шаги 1-3 для всех углов наблюдения.
5.  Повторить шаги 1-4 для всех углов наблюдения, пока не будет восстановлен оригинальный объект.

Обратите внимание, что обратная проекция может приводить к искажению восстановленного объекта, если проекция не была сделана в достаточном количестве направлений. Чем больше направлений используется для проекции, тем более точной будет восстановленная форма объекта.

---

Преобразование Радона - это математическая операция, которая позволяет представить двумерное изображение в виде интегралов по прямым линиям, проходящим через изображение под разными углами.

Свертка и обратная проекция - это две взаимосвязанные операции, которые позволяют обратить преобразование Радона и восстановить исходное изображение из его преобразования Радона.

Алгоритм свертки включает следующие шаги:

1.  Задать параметры преобразования Радона, такие как число углов, по которым происходит интегрирование, и шаг дискретизации углов.
2.  Применить преобразование Радона к исходному изображению, чтобы получить его преобразование Радона.
3.  Выполнить операцию свертки между преобразованием Радона и ядром свертки, которое зависит от параметров преобразования Радона. Это позволяет получить новое преобразование Радона, которое будет использоваться в обратной проекции.

Алгоритм обратной проекции включает следующие шаги:

1.  Задать параметры обратного преобразования Радона, которые должны совпадать с параметрами преобразования Радона, используемыми в алгоритме свертки.
2.  Выполнить операцию обратной свертки между новым преобразованием Радона, полученным в результате свертки, и ядром обратной свертки, которое зависит от параметров обратного преобразования Радона. Это позволяет получить набор линий, которые соответствуют исходному изображению.
3.  Интерполировать линии, чтобы получить восстановленное изображение.

Общая идея заключается в том, что преобразование Радона переводит двумерное изображение в одномерное преобразование. Затем операции свертки и обратной проекции позволяют перейти обратно от одномерного преобразования к двумерному изображению.