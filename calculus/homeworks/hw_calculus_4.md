# Домашняя работа

## Задача 1

### пункт а

---

$$
(x^2 + y^2)^3 = x^3y
$$

Нарисуем эскиз графика: 

[![hw 4 1 a](https://b.fotohosting.pro/2025/10/03/hw_4_1_a.png)](https://fotohosting.pro/i/hw-4-1-a.5KCXn)

Введем полярные корды:

$$
x = r \cos \varphi \quad y = r \sin \varphi
$$

Тогда:

$$
(x^2 + y^2)^3 = x^3y \Longleftrightarrow (r^2)^3 =r^3 \cos^3 \varphi \cdot r \sin \varphi \Rightarrow r^2 = \cos^3 \varphi \cdot \sin \varphi
$$

Так как $r^2 \geq 0$, то и $\cos^3 \varphi \cdot \sin \varphi \geq 0$

Тогда выходит, что, чтобы это выполнялось, $\cos \varphi$ и $\sin \varphi$ должны быть одинаковых знаков.

Если нарисовать триг. окружность, то получим, что это происходит в $I$ и $III$ четверти триг. окружности.

Ну или если писать формально: 

$$
\cos^3 \varphi \geq 0 \ \land \ \sin \varphi \geq 0 \Longleftrightarrow \varphi \in [0 + 2\pi n, \frac \pi 2 + 2 \pi n] \cup [\pi + 2 \pi k, \frac{3 \pi}{2} + 2\pi k], n, k \in \Z
$$

То бишь у нас есть две области для интегрирования хехех

Исходная площадь:

$$
I = \int_0^{\frac \pi 2} d \varphi \int_0^{ \sqrt{\cos^3 \varphi \sin \varphi}} |J| dr + \int_\pi^{\frac{3 \pi} 2} d \varphi \int_0^{\sqrt{\cos^3 \varphi \sin \varphi}} |J| dr = 
$$

$$
= \int_{\frac \pi 2}^\pi d \varphi \int_0^{\sqrt{\cos^3 \varphi \sin \varphi}} r dr + \int_\pi^{\frac{3 \pi} 2} d \varphi \int_\pi^{\sqrt{\cos^3 \varphi \sin \varphi}} r dr = 
$$

$$
= \frac 1 2 \int_{\frac \pi 2}^\pi \cos^3 \varphi \sin \varphi \ d \varphi + \frac 1 2 \int_\pi^{\frac{3 \pi} 2} \cos^3 \varphi \sin \varphi \ d \varphi
$$

Вычислим сначала $\int \cos^3 \varphi \sin \varphi \ d \varphi$:

$u = \cos \varphi$, тогда $du = - \sin \varphi d \varphi$

Тогда:

$$
\int \cos^3 \varphi \sin \varphi \ d \varphi = - \int u^3 du = - \frac{u^4}{4} = - \frac{\cos^4 \varphi }{4}
$$

Тогда:

$$
\int_{\frac \pi 2}^\pi \cos^3 \varphi \sin \varphi \ d \varphi = \left[- \frac{\cos^4 \varphi }{4} \right]_0^{\frac \pi 2} = 0 + \frac 1 4 = \frac 1 4
$$

Ну и посчитаем второй:

$$
\int_\pi^{\frac{3 \pi} 2} \cos^3 \varphi \sin \varphi \ d \varphi = \left[-\frac{\cos^4 \varphi}{4} \right]_\pi^{\frac{3 \pi} 2} = 0 + \frac 1 4 = \frac 1 4
$$

Тогда:

$$
I = \frac 1 2 \cdot \frac 1 4 + \frac 1 2 \cdot \frac 1 4 = \frac 1 4
$$

Ответ: $\frac 1 4$

### пункт б

---

$$
(x^2 + y^2 + y)^2 = x^2 + y^2
$$

[![hw 4 1 b](https://a.fotohosting.pro/2025/10/03/hw_4_1_b.png)](https://fotohosting.pro/i/hw-4-1-b.5KC6Z)

Введем полярные корды:

$$
x = r \cos \varphi \quad y = r \sin \varphi
$$

Тогда:

$$
(r^2 + r \sin \varphi)^2 = r^2, \ r \geq 0 \Rightarrow \begin{equation*} 
\begin{cases}
r^2 + r \sin \varphi = r
\\
r^2 + r \sin \varphi = -r
\end{cases}
\end{equation*} \Rightarrow \begin{equation*} 
\begin{cases}
r = 1 - \sin \varphi
\\
r = - 1 - \sin \varphi\end{cases}
\end{equation*} \Rightarrow r = 1 - \sin \varphi
$$

Ну и отсюда понятно, что $\varphi \in [0, 2 \pi]$. Тогда $r$ меняется от $0$ до $1 - \sin \varphi$. Короче получим интеграл:

$$
\int_0^{2 \pi} d \varphi \int_0^{1 - \sin \varphi} r dr = \int_0^{2 \pi} \bigg(1 - 2 \sin \varphi + \sin^2 \varphi \bigg)d \varphi = \int_0^{2 \pi} d \varphi -2 \int_0^{2 \pi} \sin \varphi d \varphi + \int_0^{2 \pi} \sin^2 \varphi =
$$

$$
= 2 \pi + 2 - 2 + \int_0^{2 \pi} \frac{1 - \cos{2 \varphi}}{2} d \varphi = 2 \pi + \frac 1 2 \int_0^{2 \pi}  d \varphi - \frac 1 2 \int_0^{2 \pi} \cos{2 \varphi} \ d \varphi = 2 \pi + \pi + 0 = 3 \pi 
$$

Ответ: $3 \pi$

### пункт с

---

$$
(2x + 3y + 1)^2 + (x - 4y - 3)^2 = 1
$$

Аля график с десмоса:

[![hw 4 1 c](https://b.fotohosting.pro/2025/10/03/hw_4_1_c.png)](https://fotohosting.pro/i/hw-4-1-c.5KC4Y)

Введем замену переменных:

$$
u = 2x + 3y + 1 \quad v = x - 4y - 3
$$

Выразим теперь $x$ и $y$ через $u$ и $v$:

$$
y = \frac{u - 2v - 7}{11} \quad x = v + \frac{4u -8v - 28}{11} + 3
$$

Найдем Якобиан данной замены переменных:

$$
J = \begin{vmatrix}
    \frac{\partial x}{\partial u} & \frac{\partial x}{\partial v}
    \\
    \\
    \frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}
\end{vmatrix} = \begin{vmatrix}
    \frac 4 {11} & \frac 3 {11}
    \\
    \\
    \frac 1 {11} & -\frac{2}{11}
\end{vmatrix} = \begin{vmatrix}
    -\frac{8}{121} - \frac{3}{121}
\end{vmatrix} = \frac 1 {11}
$$

Окей, тогда:

$$
u^2 + v^2 = 1
$$

Введем полярные корды:

$$
u = r \cos \varphi \quad v = r \sin \varphi
$$

$$
u^2 + v^2 = 1 \Longleftrightarrow r^2 = 1 = \sin^2 \varphi + \cos^2 \varphi 
$$

Так как $r^2 \geq 0$, то и $\sin^2 \varphi + \cos^2 \varphi \geq 0$, что выполняется при $\varphi \in [0, 2 \pi]$

Ну тогда посчитаем:

$$
\int_0^{2 \pi} d \varphi \int_0^1 r dr = \int_0^{2 \pi} \frac{1}{2} d \varphi = \frac 1 2 \cdot 2 \pi = \pi  
$$

_(вообще я не дурачок и знаю, что это была формула окружности, но по приколу расписал)_

Так, мы нашли площадь, заданную уравнением $u^2 + v^2 = 1$, тогда исходная плошадь по сути будет равна:

$$
J \cdot \pi = \frac 1 {11} \cdot \pi = \frac{\pi}{11}
$$

Ответ: $\frac{\pi}{11}$

## Задача 2 

### пункт а

---

$$
x^2 + y^2 \leq z \leq \sqrt{x^2 + y^2}
$$

Введем цилиндр. корды:

$$
x = r \cos \varphi \quad y = r \sin \varphi \quad z = z
$$

Тогда:

$$
r^2 \leq z \leq r
$$

что выполняется только при $r \in [0, 1]$. _(из того что $r^2 \leq r$)_

Ну а $\varphi$ меняется от $[0, 2 \pi]$. _(ни от чего не зависит, такая вся сильная и независимая)_

Окей тогда получим интеграл:

$$
\int_0^{2 \pi} d \varphi \int_0^1 dr \int_{r^2}^r r dz = \int_0^{2 \pi} d \varphi \int_0^1 r (r - r^2) dr = 
$$

$$
= \int_0^{2 \pi} d \varphi \int_0^1 r^2 dr - \int_0^{2 \pi} d \varphi \int_0^1 r^3 dr = 
$$

$$
= \frac 1 3 \int_0^{2 \pi} d \varphi - \frac{1}{4} \int_0^{2 \pi} d \varphi = \frac 1 6 \cdot \pi
$$

Ответ: $\frac \pi 6$

### пункт б

$$
\sqrt{x^2 + y^2} \geq z \quad x^2 + y^2 + z^2 \leq z
$$

Введем цилиндр. корды:

$$
x = r \cos \varphi \quad y = r \sin \varphi \quad z = z
$$

Тогда наши огр. будут иметь вид:

$$
r \geq z \quad r^2 + z^2 \leq z
$$

Окей, распишем их, чтобы сделать какие-то выводы:

$$
r^2 + z^2 \leq z \Rightarrow r^2 + \left(z - \frac 1 2 \right)^2 \leq \frac 1 4 \Rightarrow 0 \leq z \leq \frac 1 2
$$

$$
r^2 + z^2 \leq z \Rightarrow r^2 \leq z - z^2 \Rightarrow r \leq \sqrt{z - z^2}
$$

Ну тогда получили, что при фикс. $z$, $r$ меняется от $z$ до $\sqrt{z - z^2}$ 

Ну а $\varphi$ опять от $0$ до $2 \pi$. Ни от чего не зависит.

Тогда получим:

$$
\int_0^{2 \pi} d \varphi \int_0^{\frac 1 2} dz \int_z^{\sqrt{z - z^2}} rdr = \int_0^{2 \pi} d \varphi \int_0^{\frac 1 2} \frac{z - z^2}{2} - \frac{z^2}{2} dz = 
$$

$$
= \frac 1 2 \int_0^{2 \pi} d \varphi \int_0^{\frac 1 2} z dz - \int_0^{2 \pi} d \varphi \int_0^{\frac 1 2} z^2 dz = 
$$

$$
= \frac{1}{16} \int_0^{2 \pi} d \varphi - \frac{1}{24} \int_0^{2 \pi} d \varphi = \frac{\pi}{24}
$$

Ответ: $\frac{\pi}{24}$

## Задача 3

$$
(x^2 + y^2 + z^2)^2 = z(x^2 + y^2)
$$

Введем сферические корды:

$$
x = r \sin \theta \cos \varphi \quad y = r \sin \theta \sin \varphi \quad z = r \cos \theta 
$$

Тогда наше ур-ие будет иметь вид:

$$
(r^2)^2 = (r^2 \sin^2 \theta \cos^2 \varphi + r^2 \sin ^2\theta \sin^2 \varphi) \cdot r \cos \theta \Rightarrow
$$

$$
\Rightarrow r^4 = (r^2 \sin^2 \theta \cdot (\cos^2 \varphi + \sin^2 \varphi)) \cdot r \cos \theta \Rightarrow
$$

$$
\Rightarrow r = \sin^2 \theta \cos \theta
$$

Откуда мы понимаем, что $r \in [0, 1]$, а $\sin^2 \theta \cos \theta \geq 0$, тк $r \geq 0$, тк $\sin^2 \theta \geq 0$, всегда то $\cos \theta \geq 0$, что происходит при $\theta \in [-\frac \pi 2 + 2 \pi n, \frac \pi 2 + 2 \pi n], n \in \Z$

Но в сфер. кордах $0 \leq \theta \leq \pi$. Поэтому в нашем случае $\theta \in \left[0, \frac \pi 2\right]$

А $\varphi$ ни от чего не зависит, поэтому $0 \leq \varphi \leq 2 \pi$!

Тогда получим вот такой интеграл:

$$
I = \int_0^{2\pi} d \varphi \int_{0}^{\frac \pi 2} \sin \theta \ d \theta \int_{0}^{\sin^2 \theta \cos \theta} r^2 dr = 
$$

$$
= \frac 1 3 \int_0^{2\pi} d \varphi \int_{0}^{\frac \pi 2} \sin^7 \theta \cdot \cos^3 \theta \ d \theta
$$

Введем замену:

$$
u = \sin \theta \quad du = \cos \theta d \theta 
$$

Тогда:

$$
\sin^7 \theta \cdot \cos^3 \theta \ d \theta = u^7 \cdot \cos^2 \theta \ du = u^7 \cdot (1 - \sin^2 \theta) \ du = u^7 \cdot (1 - u^2)du = u^7 - u^9 
$$

Тогда:

$$
\int_{0}^{\frac \pi 2} \sin^7 \theta \cdot \cos^3 \theta \ d \theta = \int_{0}^1 u^7 du - \int_{0}^1 u^9 du  = \frac 1 8 - \frac 1 {10} = \frac 1 {40}
$$

Ну и тогда:

$$
I = \frac{1}{120} \int_0^{2\pi} d \varphi = \frac \pi {60}
$$

Ответ: $\frac \pi {60}$

## задача 4

$$
\left\{ \sum_{i = 1}^n \frac{x_i}{a_i} \leq 1, \ x_i \geq 0 \right\} \quad (a_i > 0)
$$

Пусть $y_i = \frac{x_i}{a_i}$, тогда $x_i = a_i \cdot y_i$

Найдем Якобиан данной замены:

$$
J = \begin{vmatrix}
    \frac{\partial x_1}{\partial y_1} & \frac{\partial x_1}{\partial y_2} & \dots & \frac{\partial x_1}{\partial y_n}
    \\
    \\
    \frac{\partial x_2}{\partial y_1} & \frac{\partial x_2}{\partial y_2} & \dots & \frac{\partial x_2}{\partial y_n}
    \\
    \\
    \dots & \dots & \dots & \dots
    \\
    \\
    \frac{\partial x_n}{\partial y_1} & \frac{\partial x_n}{\partial y_2} & \dots & \frac{\partial x_n}{\partial y_n}
\end{vmatrix} = \begin{vmatrix}
    a_1 & 0 & \dots & 0
    \\
    0 & a_2 & \dots & 0
    \\
    \dots & \dots & \dots & \dots
    \\
    0 & 0 & \dots & a_n
\end{vmatrix} = a_1 \cdot a_2 \cdot \dotsc \cdot a_n
$$

Теперь выходит надо найти объем этой фигни:

$$
\left\{ \sum_{i = 1}^n y_i \leq 1, \ y_i \geq 0 \right\} 
$$

Давайте подумаем, как это сделать.

Сначала рассмотрим для 2D:

$y_1 + y_2 \leq 1$, $y_i \geq 0$

Получим вот такую картинку:

[![hw 4 4 1](https://a.fotohosting.pro/2025/10/03/hw_4_4_1.png)](https://fotohosting.pro/i/hw-4-4-1.5KCwf)

Это прямоугольный треугольник с катетами равными $1$. Его площадь будет равна: $\frac 1 2 \cdot 1 \cdot 1 = \frac 1 2$.

Окей, добавим $y_3$:

$y_1 + y_2 + y_3 \leq 1$. То есть по сути у нас осталось такое же основание, имею в виду этот график который прикрепил выше, но добавилась еще высота и получилась такая вот пирамидка: 

[![hw 4 4 2](https://b.fotohosting.pro/2025/10/03/hw_4_4_2.png)](https://fotohosting.pro/i/hw-4-4-2.5KGqP)

А объем этой пирамиды находится как: $\frac 1 3 \cdot h \cdot S_{осн} = \frac 1 3 \cdot 1 \cdot \frac 1 2 = \frac 1 6$

$$
y_1 \in [0, 1], \ y_2 \leq 1 - y_1, \ y_3 \leq 1 - y_1 - y_2
$$

$$
\int_0^1 dy_1 \int_0^{1 - y_1} dy_2 \int_0^{1 - y_1 - y_2} dy_3 = \int_0^1 dy_1 \int_0^{1 - y_1} \left(1 - y_1 - y_2 \right) \ dy_2 = \frac 1 2 \int_0^1 (1 - y_1)^2 dy_1 = \frac 1 2 \cdot \frac 1 3 = \frac 1 6
$$

_(для перепроверки и понимания)_

Окей, докажем, что объем в $R^n$ такой штуки равен $\frac 1 {n!}$.

База: $n = 1$, $n = 2$, $n = 3$ доказано!

Шаг: $n \to n + 1$, что попробуем доказать через интеграл. То есть мы знаем, что:

$$
\int_0^1 dy_1 \int_0^{1 - y_1} dy_2 \int_0^{1 - y_1 - y_2} dy_3 \ \dots \int_0^{1 - y_1 - y_2 - \dotsc - y_n} dy_n = \frac 1 {n!}
$$

Надо доказать что:

$$
\int_0^1 dy_1 \int_0^{1 - y_1} dy_2 \int_0^{1 - y_1 - y_2} dy_3 \ \dots \int_0^{1 - y_1 - y_2 - \dotsc - y_n} dy_n \int_0^{1 - y_1 - y_2 - \dotsc - y_n - y_{n + 1}} dy_{n+1} = \frac 1 {(n+1)!}
$$

Короче я не смогу это доказать, но я нашел [в интернете](https://ru.ruwiki.ru/wiki/%D0%A1%D0%B8%D0%BC%D0%BF%D0%BB%D0%B5%D0%BA%D1%81) формулу объема. Просто ей воспользуюсь $:)$

В общем, объем той фигни выходит равен $\frac 1 {n!}$.

Но тогда объем изначальной фигни в результате найденного Якобиана равен:

$$
\frac{a_1 \cdot a_2 \cdot \dotsc \cdot a_n}{n!}
$$

Ответ: $\frac{a_1 \cdot a_2 \cdot \dotsc \cdot a_n}{n!}$