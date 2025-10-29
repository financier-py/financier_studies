# Контрольная работа 24-25

## Вариант 1

### Задача 1

Дана функция $f(x) = \hat{k}$, где $\hat{k} = \min\set{m \in \Z \mid m \geq x}$. Необходимо вычислить интеграл: $\iint\limits_{\substack{1 \leq x \leq 4 \\ 3 \leq y \leq 5}}f(x + y)dxdy$

**Решение**:

Так как $f(x) = \hat{k}$, где $\hat{k} = \min\set{m \in \Z \mid m \geq x}$, то это эквивалентно тому, что $f(x) = \lceil x \rceil$

Поэтому интеграл превращается в:

$$
\iint\limits_{\substack{1 \leq x \leq 4 \\ 3 \leq y \leq 5}}\lceil x + y \rceil dxdy
$$

На нашей области интегрирования сумма $x + y$ меняется в пределах:

$$
1 + 3 \leq x + y \leq 4 + 5 \Longleftrightarrow 4 \leq x+y \leq 9
$$

Разобьем нашу область интегрирования на 5 частей:

- $4 < x + y \leq 5$ $\Longrightarrow \lceil x + y \rceil = 5$, площадь интегрирования: $S_5$
- $5 < x + y \leq 6$ $\Longrightarrow \lceil x + y \rceil = 6$, площадь интегрирования: $S_6$
- $6 < x + y \leq 7$ $\Longrightarrow \lceil x + y \rceil = 7$, площадь интегрирования: $S_7$
- $7 < x + y \leq 8$ $\Longrightarrow \lceil x + y \rceil = 8$, площадь интегрирования: $S_8$
- $8 < x + y \leq 9$ $\Longrightarrow \lceil x + y \rceil = 9$, площадь интегрирования: $S_9$

Случай, когда $\lceil x + y \rceil = 4$ получается, если $x = 1 \land y = 3$, но это мера нуль!

Тогда искомый интеграл разобьется на сумму!

$$
\iint\limits_{\substack{1 \leq x \leq 4 \\ 3 \leq y \leq 5}}\lceil x + y \rceil dxdy = \sum_{n = 5}^9 n \cdot S_n
$$

Осталось найти площади!

$S_5$:

$4 < x + y \leq 5 \Longrightarrow y > 4 - x \land y \leq 5 - x \Longrightarrow y \in (4-x, 5-x]$, при этом $x \in [1, 4]$ 

Но так как $y \in [3, 5]$, то $y \in [3, 5-x]$, но тогда $x \in [1, 2]$

Тогда:

$$
S_5 = \int_1^2 dx \int_3^{5 - x} dy = \int_1^2 (2 - x) dx = 2 - \frac{3}{2} = \frac{1}{2}
$$

$S_6$:

$5 < x + y \leq 6 \Longrightarrow y > 5 - x \land y \leq 6 -x \Rightarrow y \in (5 - x, 6 - x]$ для каждого фикс. $x \in [1, 4]$

Тогда:

$$
\int_1^2 dx \int_{5 - x}^{6 - x} dy + \int_2^3 dx \int_3^{6 - x} dy = 1 + \int_2^3 (3 - x)dx = 1 + 4,5 - 4 = 1,5
$$

$S_7$:

$y \in (6 - x, 7 - x]$ для каждого фикс. $x \in [1, 4]$

$$
\int_1^2 dx \int_{6 - x}^5 dy + \int_2^3 dx \int_{6 - x}^{7 - x} dy + \int_3^4 dx \int_3^{7 - x} dy = 
$$

$$
\int_1^2 (x - 1)dx + 1 + \int_3^4 (4 - x)dx = \frac 1 2 + 8 - 7,5 + 1 = 2 
$$

$S_8$:

$7 < x + y \leq 8 \Longrightarrow y > 7 -x \land y \leq 8 -x \Longrightarrow y \in (7 - x, 8 - x]$ для любого фикс. $x \in [1, 4]$

$$
\int_2^3 dx \int_{7 - x}^5 dy + \int_3^4 dx \int_{7 - x}^{8 - x} dy = 1 + \int_2^3 (x - 2)dx = 1 + - \frac 3 2 + 2 = \frac{3}{2}
$$

$S_9$:

$8 < x + y \leq 9 \Longrightarrow y \in (8 - x, 9 - x]$ для каждого фикс $x \in [1, 4]$

Тогда:

$$
\int_3^4 dx \int_{8 - x}^5 dy = \int_3^4 (x - 3)dx = -4 + 4,5 = \frac{1}{2}
$$

Тогда искомый интеграл равен:

$$
\sum_{n = 5}^9 n \cdot S_n = 5 \cdot 0,5 + 6 \cdot 1,5 + 7 \cdot 2 + 8 \cdot 1,5 + 9 \cdot 0,5 = 
$$

$$
2,5 + 9 + 14 + 12 + 4,5 = 19 + 23 = 42
$$

Ответ: 42

На самом деле мы интегрировали как раз по этой области. Прямые здесь - ограничения. Поэтому с графиком становится понятнее, как именно надо расставлять пределы интегрирования!

[![image](https://a.fotohosting.pro/2025/10/29/image1977f387139aeddb.png)](https://fotohosting.pro/i/image.NxRWz)

### Задача 2

Вычислить интеграл:

$$
\int_{-2}^1 dz \int_0^1 dy \int_{\arcsin(y)}^\frac{\pi}{2} \cos^5(x) \sqrt{1 + \cos^6(x)} \ dx
$$

Интеграл $\int \cos^5(x) \sqrt{1 + \cos^6(x)} \ dx$ решается крайне сложно. Если он вообще выражается через элементарные функции. Поэтому попробуем сменить порядок интегрирования!

Заметим, что $z$ ни от чего не зависит. А вот $\arcsin(y) \leq x \leq \frac{\pi}{2}$. Из $\arcsin(y) \leq x$ получим: $y \leq \sin(x)$

При $y \in [0, 1]$:  $x$ принимает значения из промежутка $\left[0, \frac{\pi}{2} \right]$

Поэтому для каждого фикс. $x \in \left[0, \frac{\pi}{2} \right]$ $y$ будет принимать значения $[0, \sin(x)]$

Поэтому получим новые пределы интегрирования:

$$
I = \int_{-2}^1 dz \int_0^\frac{\pi}{2} dx \int_0^{\sin(x)} \cos^5(x) \sqrt{1 + \cos^6(x)} dy
$$

Очевидно, что тут $x$ выступает как константа, поэтому:

$$
\int_0^{\sin(x)} \cos^5(x) \sqrt{1 + \cos^6(x)} dy = \cos^5(x) \sqrt{1 + \cos^6(x)} \sin(x)
$$

Теперь вычислим:

$$
J = \int \cos^5(x) \sqrt{1 + \cos^6(x)} \sin(x) dx
$$

Пусть $u = \cos(x)$, тогда $du = -\sin(x)$, получим:

$$
J = - \int u^5 \sqrt{1 + u^6}du
$$

Пусть $t = 1 + u^6$, тогда $dt = 6u^5du$, получим:

$$
J = - \frac{1}{6} \int t^\frac{1}{2}dt = - \frac{1}{9}t^{\frac{3}{2}} + C = - \frac{1}{9} (1 + u^6)^\frac{3}{2} + C = - \frac{1}{9} (1 + \cos^6(x))^\frac{3}{2} + C
$$

Тогда:

$$
\int_0^\frac{\pi}{2} \cos^5(x) \sqrt{1 + \cos^6(x)} \sin(x) dx = - \frac{1}{9} + \frac{1}{9} 2\sqrt{2} = \frac{1}{9}(2\sqrt{2} - 1)
$$

Тогда имеем:

$$
I = \frac{1}{9}(2\sqrt{2} - 1) \int_{-2}^1 dz = \frac{1}{3}(2\sqrt{2} - 1)
$$

Ответ: $\frac{1}{3}(2\sqrt{2} - 1)$

### Задача 3

Найти площадь фигуры, ограниченной кривой:

$$
(x^2 + y^2 + 2y + 1)^2 = x^2 - y^2 - 2y  - 1
$$

Посмотрим повнимательнее на равенство выше и заметим:

$$
(x^2 + (y + 1)^2)^2 = x^2 - (y + 1)^2
$$

Сделаем замену: $u = y + 1$, тогда имеем:

$$
(x^2 + u^2)^2 = x^2 - u^2
$$

Введем полярные координаты:

$$
\begin{equation*} \begin{cases}
    x = r \cos \varphi
\\
    u = r \sin \varphi

\end{cases}
    
\end{equation*} 
$$

где $r \geq 0$, $\varphi \in [0, 2\pi)$ и $x^2 + u^2 = r^2$

Тогда получим уравнение кривой в полярных кордах:

$$
r^4 = r^2(\cos^2 \varphi - \sin^2 \varphi) \Longleftrightarrow r^4 = r^2(\cos 2 \varphi)
$$

$$
\Longrightarrow r^2 = \cos 2 \varphi
$$

Так как $r^2 \geq 0$, то и $\cos 2 \varphi \geq 0$, что выполняется при $\frac{3 \pi}{2} \leq 2 \varphi < 2 \pi$ и при $0 \leq  2 \varphi \leq \frac{\pi}{2}$

Тогда получим два промежутка: $\varphi \in [\frac{3 \pi}{4}, \pi) \cup [0, \frac{\pi}{4}]$

Перейдем к поиску площади:

$$
\int_{\frac{3 \pi}{4}}^\pi d \varphi \int_0^{\sqrt{\cos 2 \varphi}} r dr + \int_{0}^\frac{\pi}{4} d \varphi \int_0^{\sqrt{\cos 2 \varphi}} r dr = 
$$

$$
\int_{\frac{3 \pi}{4}}^\pi \cos 2 \varphi \ d \varphi + \int_{0}^\frac{\pi}{4} \cos 2 \varphi \ d \varphi = 
$$

$$
= \frac{1}{2} + \frac{1}{2} = 1
$$

Ответ: $1$

### Задача 4

Нам дана поверхность, заданная уравнением:

$$
z = 1 + x - \frac{6}{5}y^\frac{5}{2}
$$

Необходимо найти площадь части, вырезанной циллиндром:

$$
D = \set{(x, y, z) \in \R^3 \mid 0 \leq x \leq 1, \ \sqrt{x} \leq y \leq 1}
$$

Для начала вспомним формулу площади поверхности: 

$$
S = \iint\limits_D \sqrt{\big(f'_x(x, y) \big)^2 + \big(f'_y(x, y) \big)^2 + 1} \ dx dy
$$

Прекрасно, найдем тогда частные производные!

$$
\frac{\partial z}{\partial x} = 1 \quad \frac{\partial z}{\partial y} = -3y^{\frac{3}{2}}
$$

Пределы интегрирования нам уже даны, поэтому просто найдем площадь:

$$
S = \int_0^1 dx \int_{\sqrt{x}}^1 \sqrt{2 + 9y^3}dy
$$

Выглядит чутка сложно, поэтому попробуем изменить пределы интегрирования:

Из $y \geq \sqrt{x}$ следует, что $y^2 \geq x \Longleftrightarrow x \leq y^2$

Для каждого фикс. $y \in [0, 1]$ имеем $x \in [0, y^2]$. Поэтому получим:

$$
S = \int_0^1 dy \int_0^{y^2} \sqrt{2 + 9y^3} dx = \int_0^1 y^2 \sqrt{2 + 9y^3} dy
$$

Пусть $u = 2 + 9y^3$, тогда $du = 27y^2 dy$, тогда имеем:

$$
S = \frac{1}{27} \int_2^{11} \sqrt{u} \ du = \frac{2}{81}(11 \sqrt{11} - 2 \sqrt{2})
$$

### Задача 5

Вычислить интеграл:

$$
I = \iiint\limits_D e^y \frac{x - 2z}{3x - z} dx dy dz
$$

$D$ образован плоскостями:

$$
x - 2z = 2 \quad x - 2z = 3
$$

$$
3x - z = 2 \quad 3x - z = 8
$$

$$
y = 1 \quad y = 2
$$

Введем замену:

$$
\begin{equation*} \begin{cases}
    u = x - 2z
\\
    v = 3x - z

\end{cases}
    
\end{equation*} 
$$

Выразим теперь $x$ и $z$ через $u$ и $v$. Это потребуется для нахождения матрицы Якоби и Якобиана в последствии.

$$
\begin{equation*} \begin{cases}
    x = u + 2z
\\
    z = \frac{v - 3u}{5}

\end{cases}
    
\end{equation*} \Longleftrightarrow

\begin{equation*} \begin{cases}
    x = \frac{2v - u}{5}
\\
    z = \frac{v - 3u}{5}

\end{cases}
    
\end{equation*}
$$

Вычислим Якобиан замены:

$$
J = \begin{vmatrix}
    \frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} 
    \\
    \frac{\partial z}{\partial u} & \frac{\partial z}{\partial v} 
\end{vmatrix} = \begin{vmatrix}
    - \frac{1}{5} & \frac{2}{5}
    \\
    - \frac{3}{5} & \frac{1}{5}
\end{vmatrix} = - \frac{1}{25} + \frac{6}{25} = \frac{1}{5}
$$

После замены выходит, что $D$ образован плоскостями:

$$u = 2 \quad u = 3$$

$$v = 2 \quad v = 8$$

$$y = 1 \quad y = 2$$

Поэтому пределы интегрирования становятся очевидны. 

$$
I = \int_2^8 dv \int_2^3 du \int_1^2 e^y \frac{u}{v} \cdot |J|dy= 
$$

$$
= \frac{1}{5} e(e - 1)\int_2^8 dv \int_2^3 \frac{u}{v} du = 
$$

$$
\frac{1}{2} e(e - 1) \int_2^8 v^{-1}dv = \frac{1}{2} e(e - 1)(\ln8 - \ln2)
$$

Ответ: $\frac{1}{2} e(e - 1) \ln 4$