# Домашняя работа

## задача 3:

$$
I = \int_0^2 dz \int_0^{z^2} dy \int_0^{y-z} (2x - y) dx
$$

Будем считать внутренние, потом подставлять и так получим ответ:

$$
\int_0^{y-z} (2x - y) dx = (x^2 - yx) \big|_0^{y-z} = (y-z)^2 - y(y-z) = z^2 - yz
$$


$$
\int_0^{z^2} (z^2 - yz) dy = (z^2 y - \frac{z}{2} y^2) \big|_0^{z^2} = z^4 - \frac{1}{2} z^5
$$


$$
\int_0^{2} (z^4 - \frac{1}{2} z^5) dz = ( \frac{1}{5} z^5 - \frac{1}{12} z^6 ) \big|_0^2 = \frac{32}{5} - \frac{16}{3} = \frac{16}{15}
$$

$$
\Rarr I = \frac{16}{15}
$$

Ответ: $\frac{16}{15}$

## задача 5:

$$
I = \int_0^4 dz \int_{-z}^z dx \int_0^{\sqrt{z^2 - x^2}} z^2xy^2dy
$$

$$
\int_0^{\sqrt{z^2 - x^2}} z^2xy^2dy = \frac{z^2x}{3} \cdot y^3 \big|_0^{\sqrt{z^2 - x^2}} = \frac{z^2}{3} \cdot x (z^2 - x^2)^{\frac{3}{2}}
$$

Выходит теперь надо вычислить: $J = \int_{-z}^z \frac{z^2}{3} \cdot x (z^2 - x^2)^{\frac{3}{2}} dx$

Пусть $f(x) = \frac{z^2}{3} \cdot x (z^2 - x^2)^{\frac{3}{2}}$, где $z$ - константа.

Тогда $f(-x) = -\frac{z^2}{3} \cdot x (z^2 - x^2)^{\frac{3}{2}} = -f(x) \Rarr f(x)$ - нечетная функция. 

Тогда $J = \int_{-z}^z f(x) dx = 0 \Rarr I = 0$ 

Ответ: 0

## задача 6:

$$
I = \int_0^1 dx \int_x^1 dy \int_y^1 e^{z^3} dz = \iiint_D e^{z^3} dx dy dz
$$

где $D = \{(x, y, z) \ | \ 0 \leq x \leq 1, \ x \leq y \leq 1, \ y \leq z \leq 1 \}$, отсюда получаем: $0 \leq x \leq y \leq z \leq 1$

Выходит, если хотим поменять порядок интегрирования, то видим, что $z$ меняется от $0$ до $1$, при фикс. $z$, $x$ меняется от $0$ до $z$, а при фикс. $x$ и $z$, $y$ меняется от $x$ до $z$.

Итого $D = \{(x, y, z) \ | \ 0 \leq z \leq 1, \ 0 \leq x \leq z, \ x \leq y \leq z \}$

$$
\rArr I = \int_0^1dz \int_0^z dx \int_x^z e^{z^3}dy =
$$

$$
= \int_0^1dz \int_0^z (z \cdot  e^{z^3} - x \cdot e^{z^3}) dx = 
$$

$$
= \int_0^1 (z^2 e^{z^3} - \frac{z^2 e^{z^3}}{2}) dz = \frac{1}{2} \int_0^1 z^2 e^{z^3} dz
$$

Пусть $u = z^3$, тогда $du = 3z^2dz$

Тогда $\int  z^2 e^{z^3} dz = \frac{1}{3} \int e^udu = \frac{1}{3}e^u + C = \frac{1}{3}e^{z^3} + C$

$$
\rArr I = \frac{1}{6} (e^{z^3}) \big|_0^1 = \frac{1}{6} \cdot (e - 1)
$$

Ответ: $\frac{1}{6} (e - 1)$