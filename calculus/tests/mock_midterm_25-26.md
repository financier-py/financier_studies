# Задачи для подготовки

## Задача 1

$$
\iint\limits_{\substack{0 \leq x \leq 4 \\ 0 \leq y \leq 3}} x^3 y \ dx dy
$$

Необходимо вычислить данный интеграл как предел интегральной суммы

Разобьем отрезок $[0, 4]$ на $n$ равных частей. Тогда получим, что длина одной части будет равна: $\frac{4 - 0}{n} = \frac{4}{n}$

Также разобьем отрезок $[0, 3]$ на $n$ равных частей, длина одной части будет: $\frac{3}{n}$

Тогда вся область разобьется на $n^2$ прямоугольников! Площадь любого будет равна: $\frac{4}{n} \cdot \frac{3}{n} = \frac{12}{n^2}$

Тогда любой прямоугольник в разбиении описывается так:

$$\left[\frac{(i - 1)4}{n}, \frac{4i}{n} \right] \times \left[\frac{(j - 1)3}{n}, \frac{3j}{n} \right]$$

где $i \in \set{1, 2, \dotsc, n}$ и $j \in \set{1, 2, \dotsc, n}$

Так как в качестве $\xi_i$ мы выбираем верхние правые ячейки, то в нашем случае это будет соответствовать точкам: 

$$
\xi_{ij} = \left(\frac{4i}{n},  \frac{3j}{n} \right)
$$

Перейдем к вычислению интеграла!

$$
\sum_{i = 1}^n \sum_{j = 1}^n \frac{12}{n^2} \cdot \frac{64i^3}{n^3} \cdot \frac{3j}{n} = \frac{2304}{n^6} \sum_{i = 1}^n \sum_{j = 1}^n i^3 j =
$$

$$
= \frac{1152 (n + 1)}{n^5} \sum_{i = 1}^n i^3 = \frac{288 (n + 1)^3}{n^3}
$$

Перейдем к пределу:

$$
\lim_{n \to \infty} \frac{288 (n + 1)^3}{n^3} = 288
$$

Ответ: $288$

## Задача 2

Имеем такое задание:

[![image](https://a.fotohosting.pro/2025/10/29/image443023b10267ced0.png)](https://fotohosting.pro/i/image.R7F8y)

Фото вставил, чтобы была видна область интегрирования

Видим, что $y \in [-1, 1]$. Разобьем данную область на две. 

В первой $y \in [-1, 0]$. Справа $x$ ограничен кривой $x = y - y^3$, а слева прямой $x = -1$

Поэтому для фикс. $y:$ $x \in [-1, y - y^3]$

Во второй $y \in [0, 1]$. Справа $x$ также ограничен кривой $x = y - y^3$

Слева же имеем $y = (x+1)^2$. Так как у нас $y \geq 0$, то $x = \sqrt{y} - 1$

Поэтому слева $x$ уже ограничен кривой $x = \sqrt{y} - 1$

Поэтому для фикс. $y:$ $x \in [\sqrt{y} - 1, y - y^3]$

Так как мы получили по сути пределы интегрирования, то посчитаем сам интеграл:

$$
\int_{-1}^0 dy \int_{-1}^{y - y^3} ydx + \int_0^1 dy \int_{\sqrt{y} - 1}^{y - y^3} y dx =
$$

$$
= \int_{-1}^0 (y^2 - y^4 + y) dy + \int_0^1 (y^2 - y^4 - y \sqrt{y} + y)dy = 
$$

$$
\frac{1}{3} - \frac{1}{5} - \frac{1}{2} + \frac{1}{3} - \frac{1}{5} + \frac{1}{2} - \frac{2}{5} = \frac{2}{3} - \frac{4}{5} = - \frac{2}{15}
$$

Ответ: $- \frac{2}{15}$

## Задача 3

Вычислить интеграл:

$$
I = \int_0^{\frac{1}{\sqrt{3}}} x dx \int_x^\frac{1}{\sqrt{3}} \frac{\arctg y}{y} dy
$$

Заметим, что вычисление интеграла $\int \frac{\arctg y}{y} dy$ может быть достаточно трудоеким. А точнее он вообще не выражается через элементарные функции. Поэтому попробуем сменить пределы интегрирования

Для каждого фикс. $x \in [0, \frac{1}{\sqrt{3}}]$ имеем $y \in [x, \frac{1}{\sqrt{3}}]$. Из $y \geq x$ понимаем, что $x \leq y$

Поэтому получим пределы интегрирования: $0 \leq y \leq \frac{1}{\sqrt{3}}$ и $0 \leq x \leq y$

Получим:

$$
I = \int_0^\frac{1}{\sqrt{3}} \frac{\arctg y}{y} dy \int_0^y xdx = \frac{1}{2} \int_0^\frac{1}{\sqrt{3}} y \arctg y \ dy
$$

Вычислим $J = \int y \arctg y \ dy$

Используем интегрирование по частям:

Пусть $u = \arctg y$, тогда $du = \frac{dy}{y^2 + 1}$, $dv = ydy$, тогда $v = \frac{y^2}{2}$

$$
J = \frac{y^2 \arctg y}{2} - \frac 1 2 \int \frac{y^2}{y^2 + 1} dy = \frac{y^2 \arctg y}{2} - \frac 1 2 \int \left(1 - \frac{1}{y^2 + 1} \right)dy = 
$$

$$
= \frac{y^2 \arctg y}{2} - \frac 1 2 y + \frac{1}{2} \arctg y + C = \frac{1}{2} \arctg y (y^2 + 1) - \frac{1}{2}y + C
$$

$$
\arctg \left(\frac{1}{\sqrt{3}} \right) = \frac{\pi}{6}
$$

Поэтому:

$$
I = \frac{\pi}{12} + \frac{\pi}{36} - \frac{1}{2 \sqrt{3}} = \frac{\pi}{9} - \frac{1}{2 \sqrt{3}}
$$

Ответ: $\frac{\pi}{9} - \frac{1}{2 \sqrt{3}}$

## Задача 4

$$(x^2 + y^2 - y)^2 = x^2 + y^2$$

Введем полярные координаты:

$$
\begin{equation*} \begin{cases}
    x = r \cos \varphi
\\
    y = r \sin \varphi

\end{cases}
    
\end{equation*} 
$$

где $r \geq 0$ и $0 \leq \varphi \leq 2 \pi$

Тогда:

$$
(r^2 - r\sin \varphi)^2 = r^2
$$

Избавимся от квадратов, но это породит два случая:

- $r^2 - r\sin \varphi = r \leftrightarrow r(r - \sin \varphi - 1) = 0$
- $r^2 - r\sin \varphi = -r\leftrightarrow r(r - \sin \varphi + 1) = 0$

В первом случае получим, что или $r = 0$, или $r = \sin \varphi + 1$. Так как $r \geq 0$ это наложит ограничение: $\sin \varphi \geq -1$, что выполняется $\forall \varphi \in [0, 2 \pi]$

Во втором случае: или $r = 0$, или $r = \sin \varphi - 1$. Так как $r \geq 0$ это наложит ограничение: $\sin \varphi \geq 1$, что выполняется только при $\varphi = \frac{\pi}{2}$

Таким образом понимаем, что кривая описывается так:

$$
r = \sin \varphi + 1
$$

Найдем площадь фигуры:

$$
\int_0^{2 \pi} d \varphi \int_0^{\sin \varphi + 1} r dr = \frac{1}{2} \int_0^{2 \pi} (\sin^2 \varphi + 2 \sin \varphi + 1) d \varphi = 
$$

$$
= \frac{1}{2} \int_0^{2 \pi} \sin^2 \varphi d \varphi + \int_0^{2 \pi} \sin \varphi d \varphi + \pi = 
$$

$$
= \frac{1}{4} \int_0^{2 \pi} \cos 2 \varphi d \varphi + \frac{1}{4} \int_0^{2 \pi} d \varphi + \pi = 
$$

$$
= \frac{1}{2} \pi + \pi = \frac{3 \pi }{2} 
$$

## Задача 5

$$
\int_{-1}^0 dy \int_{- \sqrt{1 - y^2}}^0 dx \int_{\sqrt{x^2 + y^2}}^{\sqrt{2 - x^2 - y^2}} z^2 dz
$$

Введем циллиндрические координаты:

$$
\begin{equation*} \begin{cases}
    x = r \cos \varphi
\\
    y = r \sin \varphi
\\
    z = z
\end{cases}
\end{equation*} 
$$

Рассмотрим область интегрирования. $-1 \leq y \leq 0 \Rightarrow -1 \leq r \sin \varphi \leq 0$. Из $r \sin \varphi \leq 0$ следует, что $\sin \varphi \leq 0 \Rightarrow \varphi \in [\pi, 2 \pi)$. А из $r \sin \varphi \geq -1$ следует, что $r \in [0, 1]$

Также из второго имеем $r \cos \varphi \leq 0$. Поэтому $\varphi \in \left[\pi, \frac{3\pi}{2}\right]$

Получим:

$$
I = \int_0^1 r dr \int_\pi^\frac{3\pi}{2} d \varphi \int_r^{\sqrt{2 - r^2}} z^2 dz
$$

Посчитаем сначала внутренний:

$$
\int_r^{\sqrt{2 - r^2}} z^2 dz = \frac{(2 - r^2)^\frac{3}{2} - r^3}3
$$

Тогда:

$$
I = \frac{\pi}{6} \int_0^1 r (2 - r^2)^\frac{3}{2} dr - \frac{\pi}{6} \int_0^1 r^4 dr
$$

По очереди вычислим.

$$
J = \int_0^1 r (2 - r^2)^\frac{3}{2} dr
$$

Пусть $u = 2 - r^2$, тогда $du = -2r$, тогда имеем:

$$
J = - \frac{1}{2} \int_2^1 u^\frac{3}{2} du = \frac{1}{2} \int_1^2 u^\frac{3}{2} du = \frac{1}{5} \cdot (4 \sqrt 2 - 1)
$$

К следующему:

$$
\int_0^1 r^4 dr = \frac{1}{5}
$$

Тогда:

$$
I = \frac{\pi}{30} (4 \sqrt 2 - 2) = \frac{\pi}{15} (2 \sqrt{2} - 1)
$$

Ответ: $\frac{\pi}{15} (2 \sqrt{2} - 1)$

## Задача 6

Необходимо найти площадь поверхности:

$$
2y + 4z - x^2 = 5
$$

Выразим отсюда $z$:

$$
z = \frac{1}{4}x^2 - \frac{1}{2} y + \frac{5}{2}
$$

Вспомним формулу площади поверхности:

$$
S = \iint\limits_D \sqrt{(f'_x(x, y))^2 + (f'_y(x, y))^2 + 1} \ dx dy
$$

Найдем тогда частные производные:

$$
\frac{\partial z}{\partial x} = \frac{1}{2}x \quad \frac{\partial z}{\partial y} = - \frac{1}{2}
$$

Теперь проанализируем область интегрирования $D$. Это треугольник с вершинами $(0, 0), \ (2, 0)$ и $(2, 4)$.

Посмотрим на его график:

[![image](https://a.fotohosting.pro/2025/10/29/imaged73b048681615400.png)](https://fotohosting.pro/i/image.R98Ag)

Несложно понять, что прямая, проходящая через точки $(0, 0)$ и $(2, 4)$ это $y = 2x$

Поэтому для каждого фикс. $x$ из $[0, 1]$ $y$ принимает значения: $0 \leq y \leq 2x$

Прекрасно! Теперь найдем тогда площадь!

$$
S = \int_0^2 dx \int_0^{2x} \sqrt{\frac{1}{4}x^2 + \frac{5}{4}}\ dy =
$$

$$
= \int_0^2 \frac{1}{2}2x  \sqrt{x^2 + 5} \ dx = \int_0^2 x  \sqrt{x^2 + 5} \ dx
$$

Пусть $u = x^2 + 5$, тогда $du = 2x$, получим:

$$
S = \frac{1}{2} \int_5^9 \sqrt u \ du = \frac{1}{3} (9 \sqrt{9} - 5 \sqrt{5})
$$

Ответ: $\frac{1}{3} (27 - 5 \sqrt{5})$