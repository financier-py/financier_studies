# Домашняя работа

## задача 2

$$
I = \int_{-2}^2 dy \int_{- \sqrt{4-y^2}}^{\sqrt{4-y^2}} dx \int_{- \sqrt{4 - x^2 -y^2}}^{\sqrt{4 - x^2 -y^2}} (x^2z +y^2z + z^3)dz
$$

Несложно догадаться, что область интегрирования - шар радиуса 2:

$y$ идет от $-2$ до $2$, для каждого фикс. $y$, $x \in [-\sqrt{4-y^2}, \sqrt{4-y^2}]$, то есть $x^2 + y^2 \leq 4$.

А для каждого фикс. $x$ и $y$, $z \in [-\sqrt{4-x^2-y^2}, \sqrt{4-x^2-y^2}]$, то есть $x^2 + y^2 + z^2 \leq 4$

#### Сферическая замена:

$$
x = r \sin(\theta) \cos(\varphi)
$$

$$
y = r \sin(\theta) \sin(\varphi)
$$

$$
z = r \cos(\theta)
$$

#### Теперь разберемся с функцией:

$$
x^2z +y^2z + z^3 = z(x^2 + y^2 + z^2) = r\cos(\theta) \cdot r^2 = r^3 \cos(\theta)
$$

#### Факт, который мы знаем:

$$
dxdydz = r^2 \sin(\theta) dr d\theta d\varphi
$$

Тогда:

$$
I = \int_0^{2\pi} d\varphi \int_0^\pi d\theta \int_{0}^2 r^3\cos(\theta) \cdot r^2\sin(\theta) dr = 
$$

$$
= \int_0^{2\pi} d\varphi \int_0^\pi d\theta \int_{0}^2 r^5 \cos(\theta) \sin(\theta) dr = 
$$

$$
= \int_0^{2\pi} d\varphi \int_0^\pi \frac{32}{3} \cos(\theta) \sin(\theta) d\theta =
$$

$$
=  \int_0^{2\pi} d\varphi \int_0^\pi \frac{32}{6} \sin(2 \theta) d\theta = 
$$

$$
= \int_0^{2\pi} \frac{32}{6} \cdot (-\frac{1}{2} \cos(2\theta)) \big|_0^\pi d\varphi =
$$

$$
= \int_0^{2\pi} 0 d\varphi = 0
$$

Ответ: $0$

## задача 3

### а) 
$$
I = \iint\limits_{\substack{1 \leq x^2 + y^2 \leq 49 \\ y \geq 0}} \frac{\ln(x^2 + y^2)}{x^2 + y^2} \, dx\, dy
$$

Знаем, что $D = \{(x, y) \ | \ 1 \leq x^2 + y^2 \leq 49 , \ y \geq 0 \}$

#### Полярные координаты:

$x = r \cos(\varphi)$

$y = r \sin(\varphi)$

Тогда так как $r = \sqrt{x^2 + y^2}$ и $r \geq 0$, то из огр. $1 \leq x^2 + y^2 \leq 49$ следует, что $1 \leq r^2 \leq 49 \ \rArr \ 1 \leq r \leq 7$.

А так как $y \geq 0$, то $r \sin(\varphi) \geq 0$,  но тк $r > 0 \ \rArr \ \sin(\varphi) \geq 0 \ \rArr \ \varphi \in [0, \pi]$.

#### Разберемся с функцией:

$$
\frac{\ln(x^2 + y^2)}{x^2 + y^2} = \frac{\ln(r^2)}{r^2}
$$

#### Известный факт:

$$
dxdy = rd\varphi dr
$$

$$
\rArr \ I = \int_0^\pi d\varphi \int_1^7 \frac{\ln(r^2)}{r^2} \cdot r \ dr = 
$$

$$
= \int_0^\pi d\varphi \int_1^7 \frac{\ln(r^2)}{r} \ dr =
$$

$$
= \int_0^\pi d\varphi \int_1^7 2 \cdot \frac{\ln(r)}{r} \ dr
$$

#### Посчитаем внутренний:

$\int_1^7 2 \cdot \frac{\ln(r)}{r} \ dr$

Пусть $t = \ln(r)$, тогда $dt = \frac{1}{r}dr$

$\rArr \ \int 2 \cdot \frac{\ln(r)}{r} \ dr = \int 2t \ dt = t^2 + C = \ln^2(r) + C$

$\int_1^7 2 \cdot \frac{\ln(r)}{r} \ dr = \ln^2(r) \big|_1^7 = ln^2(7) - ln^2(1) = \ln^2(7)$

#### Вернемся:

$$
I = \ln^2(7) \int_0^\pi d\varphi = \ln^2(7) \pi
$$

Ответ: $\ln^2(7) \pi$

### б)

$$
I = \iint\limits_{x^2+y^2 \leq 2x}  \frac{xdxdy}{\sqrt{4-x^2-y^2}}
$$

#### Полярные координаты:

$$
x = r \cos \varphi, \quad y = r \sin \varphi
$$

Из огр. имеем: $x^2+y^2 \leq 2x \ \rArr \ r^2 \leq 2r \cos\varphi$, тк $r \geq 0$ в полярных кордах, то $r \leq 2 \cos\varphi$, то есть $\cos\varphi \geq 0 \ \rArr \varphi \in [-\frac{\pi}{2}, \frac{\pi}{2}]$.

#### Разберемся с функцией:

$$
\frac{x}{\sqrt{4 - (x^2 - y^2)}} = \frac{r \cos\varphi}{\sqrt{4-r^2}}
$$

#### Известный факт:

$$
dxdy = rd\varphi dr
$$

$$
\rArr \ I = \int_{\frac{-\pi}{2}}^{\frac{\pi}{2}} d\varphi \int_0^{2 \cos\varphi} \frac{r^2 \cos\varphi}{\sqrt{4-r^2}}dr
$$

#### Посчитаем внутренний:

$$
J = \int \frac{r^2}{\sqrt{4 - r^2}} \, dr
$$

Пусть $r = 2 \sin t$, тогда $dr = 2 \cos t \, dt$:

$$
J = \int \frac{4 \sin^2 t}{2 \cos t} \cdot 2 \cos t \, dt = \int 4 \sin^2 t \, dt = 2 \int (1 - \cos 2t) \, dt = 2t - \sin 2t + C
$$

Так как $t = \arcsin(\frac{r}{2})$, то:

$$
J = 2 \arcsin\left(\frac{r}{2}\right) - \frac{r \sqrt{4 - r^2}}{2} + C
$$

$$
\int_0^{2 \cos \varphi} \frac{r^2}{\sqrt{4 - r^2}} \, dr = (2 \arcsin\left(\frac{r}{2}\right) - \frac{r \sqrt{4 - r^2}}{2}) \big|_0^{2 \cos \varphi} = 2 \arcsin(\cos \varphi) - \cos \varphi \cdot \sqrt{4 - 4 \cos^2 \varphi} =
$$

$$
= 2 \arcsin(\cos \varphi) - 2 \cos \varphi |\sin \varphi|
$$

Тогда:

$$
I = \int_{-\pi/2}^{\pi/2} \cos \varphi (2 \arcsin(\cos \varphi) - 2 \cos \varphi |\sin \varphi|) d\varphi
$$


Функция четная, тк: $\cos(-\varphi) = \cos \varphi$ и $\arcsin(\cos(-\varphi)) = \arcsin(\cos \varphi)$, $|\sin(-\varphi)| = |\sin \varphi|$. Поэтому:

$$
I = 2 \int_0^{\pi/2} \cos \varphi (2 \arcsin(\cos \varphi) - 2 \cos \varphi \sin \varphi) d\varphi = 4 \int_0^{\pi/2} \cos \varphi \arcsin(\cos \varphi) \, d\varphi - 4 \int_0^{\pi/2} \cos^2 \varphi \sin \varphi \, d\varphi
$$

Тк $\arcsin(\cos \varphi) = \pi/2 - \varphi$, то

$$
I = 4 \int_0^{\pi/2} \cos \varphi \left(\frac{\pi}{2} - \varphi\right) d\varphi - 4 \int_0^{\pi/2} \cos^2 \varphi \sin \varphi \, d\varphi
$$

#### Сначала посчитаем первый:

$$
\int_0^{\pi/2} \cos \varphi \left(\frac{\pi}{2} - \varphi\right) d\varphi = \frac{\pi}{2} \int_0^{\pi/2} \cos \varphi \, d\varphi - \int_0^{\pi/2} \varphi \cos \varphi \, d\varphi
$$

$$
\int_0^{\pi/2} \cos \varphi \, d\varphi = \sin \varphi \Big|_0^{\pi/2} = 1
$$

$$
\int_0^{\pi/2} \varphi \cos \varphi \, d\varphi = (\varphi \sin \varphi + \cos \varphi) \Big|_0^{\pi/2} = \frac{\pi}{2} - 1
$$

$$
\Rarr \ \int_0^{\pi/2} \cos \varphi \left(\frac{\pi}{2} - \varphi\right) d\varphi = \frac{\pi}{2} - \frac{\pi}{2} + 1 = 1
$$

#### Теперь посчитаем второй:

$$
\int_0^{\pi/2} \cos^2 \varphi \sin \varphi \, d\varphi
$$
 Пусть $u = \cos \varphi$, тогда $du = -\sin \varphi \, d\varphi$:

$$
\int_0^{\pi/2} \cos^2 \theta \sin \theta \, d\theta = -\int_1^0 u^2 \, du = \int_0^1 u^2 \, du = \frac{1}{3}
$$

#### Объединим результаты:

$$
I = 4 - \frac{4}{3} = \frac{8}{3}
$$

Ответ: $\frac{8}{3}$

### с)

$$
I = \iiint\limits_{\substack{x^2 + y^2 \leq z^2 \\ 0 \leq z \leq 1}} (z-xy) \ dxdydz
$$

#### Цилиндрические координаты:

$$
x = r \cos\varphi \quad y = r \sin\varphi \quad z = z
$$

Рассм. огр.: 

$x^2 + y^2 \leq z^2 \ \rArr \ r^2 \leq z^2$, тк $r \geq 0$, то $r \leq |z|$

$0 \leq z \leq 1 \ \rArr \ r \leq z$

Имеем:

$z$ меняется от $0$ до $1$, при фикс. $z$, $r$ от $0$ до $z$. А $\varphi$ от $0$ до $2 \pi$, так как $x^2 + y^2 \leq z^2$ при фикс $z$ представляет круг.

#### Разберемся с функцией:

$$
z - xy = z - r^2 \cos\varphi \sin\varphi
$$

#### Известный факт:

$$
dxdydz = rd rd\varphi dz
$$

$$
\rArr \ I = \int_0^1 dz \int_0^{2 \pi} d\varphi \int_0^z (zr - r^3 \cos\varphi \sin\varphi) \ dr =
$$

$$
= \int_0^1 dz \int_0^{2 \pi} d\varphi \int_0^z zr dr - \int_0^1 dz \int_0^{2 \pi} d\varphi \int_0^z r^3 \cos\varphi \sin\varphi dr =
$$

$$
= \int_0^1 dz \int_0^{2 \pi} \frac{z^3}{2} d\varphi -\int_0^1 dz \int_0^{2 \pi} \frac{z^4}{4} \cos\varphi \sin\varphi \ d\varphi = 
$$

$$
= \int_0^1 \pi z^3 dz - \int_0^1 \frac{z^4}{8} \int_0^{2 \pi} \sin(2 \varphi) d\varphi dz =
$$

$$
= \frac{\pi}{4} + \int_0^1 \frac{z^4}{8} \cdot \left(\frac{\cos(2\varphi)}{2}\right) \Big|_0^{2\pi} \ dz =
$$

$$
= \frac{\pi}{4} + \frac{1}{8} \cdot \int_0^1 z^4 \cdot 0 \ dz = \frac{\pi}{4} + 0 = \frac{\pi}{4}
$$

Ответ: $\frac{\pi}{4}$

### д)

$$
I = \iiint\limits_{\substack{x^2 + y^2 + z^2 \geq 1 \\ x^2 + y^2 + z^2 \leq 2z}} z^2 \ dx dydz
$$

#### Сферические координаты

$$
x = r \sin\theta \cos\varphi \quad y = r \sin\theta \sin\varphi \quad z = r\cos\theta
$$

Рассм. огр.:

$x^2 + y^2 + z^2 \ \geq \ 1 \rArr r^2 \geq 1 \ \rArr \ r \geq 1$

$x^2 + y^2 + z^2 \leq 2z \ \rArr \ 2r\cos\theta \rArr r \leq 2\cos\theta$, тк $r \geq 0$, то $\cos\theta \geq 0 \ \rArr \ \theta \in [0, \frac{\pi}{2}]$

Также необходимо, чтобы верхний предел $r$ был больше нижнего, поэтому $2\cos\theta \geq 1 \ \rArr \ \theta \leq \frac{\pi}{3}$

#### Получаем такие пределы тогда: 

$r$ от $1$ до $2\cos\theta$, $\ \theta$ от $0$ до $\frac{\pi}{3}$, $\ \varphi$ от $0$ до $2\pi$

#### Известный факт:

$dxdydz = r^2 \sin\theta \ dr d\theta d\varphi$

#### Ну тогда получаем и решаем:

$$
I = \int_0^{2\pi} d\varphi \int_0^{\frac{\pi}{3}} d\theta \int_1^{2\cos\theta} r^2 \cos^2\theta \cdot r^2 \sin\theta \ dr = 
$$

$$
= \int_0^{2\pi} d\varphi \int_0^{\frac{\pi}{3}} \cos^2\theta \sin\theta \ d\theta \int_1^{2\cos\theta} r^4 \ dr =
$$

$$
= \int_0^{2\pi} d\varphi \int_0^{\frac{\pi}{3}} \cos^2\theta \sin\theta \cdot \frac{32\cos^5\theta -1}{5} \ d\theta =
$$

$$
= \frac{1}{5} \cdot \int_0^{2\pi} d\varphi \int_0^{\frac{\pi}{3}} (32\cos^7 \theta \sin \theta - \cos^2 \theta \sin \theta) d\theta 
$$

#### Решим внутренний:

$$
\int_0^{\frac{\pi}{3}} (32\cos^7 \theta \sin \theta - \cos^2 \theta \sin \theta) d\theta
$$

Пусть $u = \cos\theta$, тогда $du = -\sin\theta \ d\theta$

$$
\int_0^{\frac{\pi}{3}} (32\cos^7 \theta \sin \theta - \cos^2 \theta \sin \theta) d\theta = \int_1^{\frac{1}{2}} (32u^7 -u^2)(-du) = \int_{\frac{1}{2}}^1 (32u^7 -u^2)du =
$$

$$
= (4u^8 - \frac{u^3}{3}) \Big|_{\frac{1}{2}}^1 = \frac{709}{192}
$$

#### Вернемся:

$$
I =  \frac{1}{5} \cdot \int_0^{2\pi} \frac{709}{192} \ d\varphi = \frac{2\pi}{5} \cdot \frac{709}{192} = \frac{709\pi}{480}
$$

Ответ: $\frac{709\pi}{480}$

### я решил порешать дальше
### задача 1

$$
I = \int_{-3}^3 dx \int_0^{\sqrt{9 - x^2}} dy \int_0^{9 -x^2 -y^2} \sqrt{x^2 + y^2} \ dz = \iiint_D \sqrt{x^2 + y^2} \ dxdydz
$$

где $D = \{(x, y, z) \ | \ -3 \leq 3, \ 0 \leq y \leq \sqrt{9 -x^2}, \ 0 \leq z \leq 9 - x^2 - y^2 \}$

#### цилиндрические корды:

$$
x = r\cos\theta \quad y = r\sin\theta \quad z = z
$$

понимаем, что для фикс. $x \in [-3, 3] \quad y \in [0, \sqrt{9 - x^2}]$, то есть это эквивалентно тому, что $x^2 + y^2 \leq 9$ и $y \geq 0$ или в цилиндр. кордах: $r^2 \leq 9 \ \Longleftrightarrow \ r \in [0, 3]$ и $r\sin\theta \geq 0 \ \Longleftrightarrow \ \sin\theta \geq 0 \ \Longleftrightarrow \ 0 \leq \theta \leq \pi$

дальше, для фикс $x$ и $y$, $z \in [9 - x^2 -y^2]$ или в цилиндр. кордах: $0 \leq z \leq 9 - r^2$

Получаем, что в новых кордах пределы меняются так:

$r$ от $0$ до $3 \quad$
$\theta$ от $0$ до $\pi \quad$
$z$ от $0$ до $9 - r^2$

#### известный факт:

$$
dxdydz = r dr d\theta dz
$$

#### разберемся с функцией:

$$
\sqrt{x^2 + y^2} = \sqrt{r^2} = |r| = r
$$

#### считаем интеграл выходит:

$$
I = \int_0^\pi d\theta \int_0^3 r^2 dr \int_0^{9 - r^2} dz = \int_0^\pi d\theta \int_0^3 r^2 \cdot (9 - r^2) \ dr =
$$

$$
= 9\int_0^\pi d\theta \int_0^3 r^2 dr - \int_0^\pi d\theta \int_0^3 r^4 dr =
$$

$$
= 81 \int_0^\pi d\theta - \frac{243}{5} \int_0^\pi d\theta = \frac{162}{5} \int_0^\pi d\theta = \frac{162}{5} \pi
$$

Ответ: $\frac{162}{5} \pi$

### задача 4

$$
I = \iiint\limits_D e^x \cdot \frac{z - 2y}{5z - y}dxdydz
$$

Знаем, что $D$ образован плоскостями:

$$
z - 2y = 4 \quad z - 2y = 5
\\
5z - y = 1 \quad 5z - y = 4
\\
x = 1 \quad x = 2
$$

Сделаем замены: 

$$
u = z - 2y \quad v = 5z - y
$$

Отсюда выразим $y$ и $z$:

$$

y = \frac{v - 5u}{9} \quad z = \frac{2v - u}{9}
$$

Тогда:

$$
I = \iiint\limits_{D'} e^x \frac{u}{v} |\det{J}| \ dxdudv
$$

где $D'$ образован плоскостями:

$$
u = 4 \quad u = 5
\\
v = 1 \quad v = 4
\\
x = 1 \quad x = 2
$$

и понятно, что:

$$
\displaystyle
J = \begin{pmatrix} 

\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v} \\
\frac{\partial z}{\partial u} & \frac{\partial z}{\partial v}

\end{pmatrix} = \begin{pmatrix}
    -\frac{5}{9} & \frac{1}{9} \\
    -\frac{1}{9} & \frac{2}{9}
\end{pmatrix}
$$

тогда:

$$
\det{J} = \begin{vmatrix}
    -\frac{5}{9} & \frac{1}{9} \\
    -\frac{1}{9} & \frac{2}{9}
\end{vmatrix} = -\frac{10}{81} + \frac{1}{81} = -\frac 1 9
$$

Ну и тк теперь мы по сути интегрируем по бруску $D'$, то порядок можем выбрать любой:

т.е. $x$ меняется от $1$ до $2$, $\ v$ от $1$ до $4$, $\ u$ от $4$ до $5$

Тогда:

$$
I = \int_1^4 dv \int_4^5 -\frac u {9v} \ du \int_1^2 e^x dx = -(e^2 - e) \int_1^4 \frac 1 {9v} dv \int_4^5 u \ du =
$$

$$
= -\frac 1 9 \cdot \frac 9 2 (e^2 - e) \int_1^4 \frac 1 v dv = \frac {\ln 4} 2 \cdot (e^2 - e) = \ln 2 (e^2 - e)
$$

Ответ: $\ln 2 (e^2 - e)$