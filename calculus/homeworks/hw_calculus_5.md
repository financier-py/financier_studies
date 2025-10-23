# Домашняя работа

## задача 1

Нам дан в общем треугольник с вершинами $(0, 1), (1, 1), (1, 0)$. Пусть $x \in [0, 1]$, тогда понимаем, что для фикс. $x$, $y$ идет от $y = 1 - x$ до $y = 1$. Выходит, что нашу область можно описать как:

$$
D = \set{(x, y) \mid 0 \leq x \leq 1, 1 - x \leq y \leq 1}
$$

Как написано выше в листочке, масса тела вычисляется как 

$$
m = \iint_D \rho(x, y) dx dy
$$

Посчитаем в общем:

$$
\int_0^1 \int_{1 - x}^1 xy \ dy dx = \int_0^1 x \cdot \left[\frac{y^2} 2 \right]_{1 - x}^1 dx = \int_0^1 \left(\frac 1 2 x - \frac 1 2 x \cdot (1 - 2x + x^2) \right) dx = 
$$

$$
= \int_0^1 x^2 dx - \frac 1 2 \int_0^1 x^3 dx = \frac 1 3- \frac 1 8 = \frac 5 {24}
$$

это мы нашли массу

Теперь надо найти корды центра масс, то бишь $(x_c, y_c)$

Они ищутся согласно формулам из домашки вот так:

$$
x_c = \frac 1 m \iint_D x \cdot \rho(x, y) dx dy
$$

$$
y_c = \frac 1 m \iint_D y \cdot \rho(x, y) dx dy
$$

Ну короче найдем их:

$$
\frac 5 {24} x_c = \int_0^1 x^2 dx \int_{1 - x}^1 y dy = \int_0^1 x^2 \cdot \left[\frac{y^2} 2 \right]_{1 - x}^1 dx = \int_0^1 \left(\frac 1 2 x^2 - \frac 1 2 x^2 \cdot (1 - 2x + x^2) \right) dx = 
$$

$$
= \int_0^1 x^3 dx - \frac 1 2 \int_0^1 x^4 dx= \frac 1 4 - \frac 1 {10} = \frac 3 {20}
$$

$$
\Longrightarrow x_c = \frac 3 {20} \cdot \frac{24} 5 = \frac{18}{25}
$$

Теперь игрек:

$$
\frac 5 {24} y_c = \int_0^1 x dx \int_{1 - x}^1 y^2 dy = \int_0^1 x \cdot \left[\frac{y^3} 3 \right]_{1 - x}^1 dx = \int_0^1 \left(\frac 1 3x - \frac 1 3 x \cdot (1 - x)^3 \right) dx = 
$$

$$
= \frac 1 3 \int_0^1 x^4 dx - \int_0^1 x^3 dx + \int_0^1 x^2 dx = \frac 1 {15} - \frac 1 4 + \frac 1 3 = \frac 3{20}
$$

$$
\Longrightarrow y_c = \frac 3 {20} \cdot \frac{24} 5 = \frac{18}{25}
$$

Ответ: $\frac 5 {24}; \ \left(\frac{18}{25}, \frac{18}{25}\right)$

## задача 2

Взглянем сначала на график, чтобы полюбоваться и понять, как выглядит область $D$:

[![image](https://b.fotohosting.pro/2025/10/14/image795f1205b166cb7a.png)](https://fotohosting.pro/i/image.WvM6U)

$y = x^2 + z^2$ - красненькое, а $y = 4$ - синенькое

Понимаем, что $D$ ограничен снизу параболоидом, что можно было и так понять, ведь $x^2 + z^2 \leq 0$, а сверху плоскостью $y = 4$. Ну тогда нашу область $D$ можно описать так:

$$
D = \set{(x, y, z) \mid x^2 + z^2 \leq y \leq 4}
$$

Тут мы видим симметрию относительно оси $Oy$, поэтому будем использовать цилиндр. корды, но с осью $Oy$:

$$
\begin{equation*} \begin{cases}
    x = r \cos \varphi
\\
    z = r \sin \varphi
\\
    y = y
\end{cases}
    
\end{equation*} 
$$

Понятно, что $r \geq 0, \ \varphi \in [0, 2 \pi], \ y \in \mathbb{R}$

Посчитаем Якобиан:

$$
J = \begin{vmatrix}
    \frac{\partial x}{\partial r} & \frac{\partial x}{\partial \varphi} & \frac{\partial x}{\partial y}
\\
    \frac{\partial z}{\partial r} & \frac{\partial z}{\partial \varphi} & \frac{\partial z}{\partial y}
\\
    \frac{\partial y}{\partial r} & \frac{\partial y}{\partial \varphi} & \frac{\partial y}{\partial y}
\end{vmatrix} = \begin{vmatrix}
    \cos \varphi & - r \sin \varphi  & 0
\\
    \sin \varphi & r \cos \varphi & 0
\\
    0 & 0 & 1
\end{vmatrix} = r \cdot (\cos^2 \varphi + \sin^2 \varphi) = r
$$

Ну в целом и так понятно было, что Якобиан будет равен $r$, ибо это те же самые цилиндр. корды

Окей, тогда после замены наши огр. примут вид:

$$
r^2 \leq y \leq 4
$$

Откуда следует, что $r^2 \leq 4$, а значит $r \in [0, 2]$

Ну и тогда наша новая область интегр. будет иметь вид:

$$
D' = \set{(r, \varphi, y) \mid 0 \leq r \leq 2, \ \varphi \in [0, 2 \pi], \ r^2 \leq y \leq 4}
$$

А ф-ия плотности примет вид:

$$
\sqrt{x^2 + z^2} = \sqrt{r^2} = r
$$


Ну теперь уже найдем массу по формуле которую я указывал в первом задании:

$$
\int_0^2 r^2 dr \int_0^{2 \pi} d \varphi \int_{r^2}^4 dy = \int_0^2 2 \pi r^2 \cdot (4 - r^2) dr = 
$$

$$
= 8 \pi \int_0^2 r^2 dr - 2\pi \int_0^2 r^4 dr = \frac{64 \pi}{3} - \frac{64 \pi }{5} = \frac{128 \pi}{15}
$$

Ответ: $\frac{128 \pi}{15}$

## задача 3

Ну сначала опять налюбуемся на график, тщательно построенный в десмосе

[![image](https://b.fotohosting.pro/2025/10/14/image4cb78d1adb619dd1.png)](https://fotohosting.pro/i/image.WvbDq)

Ф-ла площади поверхности из файлика с дз вот такая:

$$
S = \iint_D \sqrt{(f'_x(x, y))^2 + (f'_y(x, y))^2 + 1} \ dx dy
$$

В нашем случае $f(x, y) = 1 - x^2 - y^2$, поэтому $f'_x(x, y) = -2x$ и $f'_y(x, y) = -2y$

Поэтому:

$$
S = \iint_D \sqrt{4x^2 + 4y^2 + 1} \ dx dy
$$

Океюшки, из условия поверхность лежит выше плоскости $z = -2$, поэтому $1 - x^2 - y^2 \geq -2 \Longleftrightarrow x^2 + y^2 \leq 3$

Поэтому наша область:

$$
D = \set{(x, y) \mid x^2 + y^2 \leq 3}
$$

Перейдем к полярным кордам:

$$
\begin{equation*} \begin{cases}
    x = r \cos \varphi
\\
    y = r \sin \varphi

\end{cases}
    
\end{equation*} 
$$

понятно, что $r \geq 0, \ \varphi \in [0, 2\pi]$

Якобиан: $dx dy = r dr d \varphi$

Из огр.: $r^2 \leq 3 \Longleftrightarrow r \in [0, \sqrt{3}]$

Ну и $\sqrt{4x^2 + 4y^2 + 1} = \sqrt{1 + 4r^2}$

В общем:

$$
S = \int_0^{\sqrt{3}} dr \int_0^{2 \pi} r \sqrt{1 + 4r^2} \ d \varphi = \pi \int_0^{\sqrt{3}} 2 r \sqrt{1 + 4r^2} \ dr
$$

Пусть $u = 4r^2$, тогда $du = 8r dr$, тогда:

$$
S = \frac{\pi}{4} \int_0^{12} \sqrt{1 + u} \ du 
$$

Пусть $t = 1 + u$, тогда $dt = du$, тогда:

$$
S = \frac{\pi}{4} \int_1^{13} t^{\frac 1 2} dt = \frac{2 \pi}{12} \cdot \left(13^{\frac 3 2} - 1 \right) = \frac{\pi}{6} \left(13 \sqrt{13} - 1 \right)
$$

Ответ: $\frac{\pi}{6} \left(13 \sqrt{13} - 1 \right)$

## задача 4

Поверхность цилиндра задана так: $x^2 + z^2 = 4$ 

Нам нужно найти ее площадь, которая лежит выше квадратика, он описывается так: $D = \set{(x, y) \mid 0 \leq x \leq 1, \ 0 \leq y \leq 1}$

тк выше квадрата, то $z \geq 0$, поэтому из $x^2 + z^2 = 4$ 
выражаем $z$ и получаем: $z = \sqrt{4 - x^2}$

[![image](https://a.fotohosting.pro/2025/10/14/image00305c962cf13fad.png)](https://fotohosting.pro/i/image.WvwsV)

Ну короче вот полюбуйтесь на график, красивый. красное - наша область интегрирования. Нижнюю часть цилиндра я срубил ибо она нафиг не нужна. 

Короче теперь надо площадь найти поверхности, она ищется так:

$$
S = \iint_D \sqrt{(f'_x(x, y))^2 + (f'_y(x, y))^2 + 1} \ dx dy
$$

Посчитаем производные в нашем случае: $f'_x(x, y) = -2x \cdot \frac{1}{2 \sqrt{4 - x^2}} = - \frac{x}{\sqrt{4 - x^2}}$, а $f'_y(x, y) = 0$

Поэтому:

$$
S = \iint_D \sqrt{\frac{x^2}{4 - x^2} + 1} \ dx dy = \iint_D \frac 2 {\sqrt{4 - x^2}} dxdy = \int_0^1 \frac 2 {\sqrt{4 - x^2}} dx \int_0^1 dy =
$$

$$
= \int_0^1 \frac 2 {\sqrt{4 - x^2}} dx = \left[2 \arcsin\left(\frac x 2 \right) \right]_0^1 = \frac{\pi}{3}
$$

Ответ: $\frac{\pi}{3}$