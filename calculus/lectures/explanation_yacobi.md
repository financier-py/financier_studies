# Матрица Якоби и Якобиан

Дано отображение:

$$
\mathbf{F}: \mathbb{R}^n \to \mathbb{R}^m
$$

$$
\mathbf{F}(x_1, x_2, ..., x_n) = 
\begin{pmatrix}
f_1(x_1, x_2, ..., x_n) \\
f_2(x_1, x_2, ..., x_n) \\
\vdots \\
f_m(x_1, x_2, ..., x_n)
\end{pmatrix}
$$

**Матрица Якоби** $J_{\mathbf{F}}$ данного отображения определяется как:

$$
J_{\mathbf{F}} = 
\begin{pmatrix}
\dfrac{\partial f_1}{\partial x_1} & \dfrac{\partial f_1}{\partial x_2} & \cdots & \dfrac{\partial f_1}{\partial x_n} \\
\\
\dfrac{\partial f_2}{\partial x_1} & \dfrac{\partial f_2}{\partial x_2} & \cdots & \dfrac{\partial f_2}{\partial x_n} \\
\\
\vdots & \vdots & \ddots & \vdots 
\\
\\
\dfrac{\partial f_m}{\partial x_1} & \dfrac{\partial f_m}{\partial x_2} & \cdots & \dfrac{\partial f_m}{\partial x_n}
\end{pmatrix}
$$

## Что такое Якобиан?

**Якобиан** — это определитель матрицы Якоби когда матрица Якоби квадратная, то есть $\mathbf{F}: \mathbb{R}^n \to \mathbb{R}^n$

### Определение

$$
\mathbf{F}(x_1, x_2, ..., x_n) = 
\begin{pmatrix}
f_1(x_1, x_2, ..., x_n) \\
f_2(x_1, x_2, ..., x_n) \\
\vdots \\
f_n(x_1, x_2, ..., x_n)
\end{pmatrix}
$$

Для $\mathbf{F}$ **Якобиан** определяется как:

$$
J = \det(J_{\mathbf{F}}) = 
\begin{vmatrix}
    \dfrac{\partial f_1}{\partial x_1} & \dfrac{\partial f_1}{\partial x_2} & \cdots & \dfrac{\partial f_1}{\partial x_n} 
    \\
    \\
    \dfrac{\partial f_2}{\partial x_1} & \dfrac{\partial f_2}{\partial x_2} & \cdots & \dfrac{\partial f_2}{\partial x_n} 
    \\
    \\
    \vdots & \vdots & \ddots & \vdots
    \\
    \\
    \dfrac{\partial f_n}{\partial x_1} & \dfrac{\partial f_n}{\partial x_2} & \cdots & \dfrac{\partial f_n}{\partial x_n}
\end{vmatrix}
$$

Принято обозначать так:

$$
J = \frac{\partial(f_1, f_2, ..., f_n)}{\partial(x_1, x_2, ..., x_n)}
$$

## Применение в кратных интегралах

При замене переменных в кратных интегралах, якобиан появляется как множитель, учитывающий изменение объема или площади, по которой мы интегрировали!

Для двойного интеграла:

$$
\iint\limits_{D} f(x,y) dxdy = \iint\limits_{D'} f(x(u,v), y(u,v)) \left|\frac{\partial(x,y)}{\partial(u,v)}\right| dudv
$$

Для тройного интеграла:

$$
\iiint\limits_{V} f(x,y,z) dxdydz = \iiint\limits_{V'} f(x(u,v,w), y(u,v,w), z(u,v,w)) \left|\frac{\partial(x,y,z)}{\partial(u,v,w)}\right| dudvdw
$$

Чтобы лучше понять интуицию, рассмотрим двумерный случай!

### Двумерный случай 

Рассмотрим отображение из плоскости $(u,v)$ в плоскость $(x,y)$:

$$
x = x(u,v), \quad y = y(u,v)
$$

Матрица Якоби:

$$
J = \begin{pmatrix}
\frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} \\
\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}
\end{pmatrix}
$$

Якобиан — определитель этой матрицы:

$$
J = \frac{\partial(x,y)}{\partial(u,v)} = \frac{\partial x}{\partial u} \frac{\partial y}{\partial v} - \frac{\partial x}{\partial v} \frac{\partial y}{\partial u}
$$

### Геометрически поймем

Рассмотрим маленький прямоугольник в плоскости $(u,v)$ со сторонами $\Delta u$ и $\Delta v$. Его площадь: $\Delta A_{uv} = \Delta u \cdot \Delta v$.

При отображении в плоскость $(x,y)$ этот прямоугольник превращается в параллелограмм. Векторы сторон:
- $\vec{a} = \left( \frac{\partial x}{\partial u} \Delta u, \frac{\partial y}{\partial u} \Delta u \right)$
- $\vec{b} = \left( \frac{\partial x}{\partial v} \Delta v, \frac{\partial y}{\partial v} \Delta v \right)$

Площадь параллелограмма равна модулю векторного произведения:

$$
\Delta A_{xy} = |\vec{a} \times \vec{b}| = \left| \frac{\partial x}{\partial u} \frac{\partial y}{\partial v} - \frac{\partial x}{\partial v} \frac{\partial y}{\partial u} \right| \Delta u \Delta v = |J| \Delta A_{uv}
$$

То есть мы увидели что, **якобиан показывает коэффициент изменения площади** при отображении.

### Обобщим на n-мерный случай $:)$

Рассмотрим $\mathbf{F}: \mathbb{R}^n \to \mathbb{R}^n$:

Пусть $\mathbf{x} = \mathbf{F}(\mathbf{u})$


Линейное приближение:

$$
\mathbf{x} \approx \mathbf{F}(\mathbf{u}_0) + J_{\mathbf{F}}(\mathbf{u}_0)(\mathbf{u} - \mathbf{u}_0)
$$
где $J_{\mathbf{F}}$ — матрица Якоби.

Рассмотрим n-мерный параллелепипед в $U$-пространстве с ребрами:

$$
\vec{e}_1 = (\Delta u_1, 0, ..., 0), \quad \vec{e}_2 = (0, \Delta u_2, ..., 0), \quad ..., \quad \vec{e}_n = (0, 0, ..., \Delta u_n)
$$

Его объем: $\Delta V_u = \Delta u_1 \Delta u_2 \cdots \Delta u_n$

При отображении векторы преобразуются по правилу:

$$
\vec{v}_k = J_{\mathbf{F}} \cdot \vec{e}_k
$$

Это означает, что столбцы матрицы, задающей преобразованный параллелепипед, — это в точности столбцы матрицы Якоби, умноженные на соответствующие $\Delta u_k$.

Объем параллелепипеда, натянутого на векторы $\vec{v}_1, ..., \vec{v}_n$, равен модулю определителя матрицы, составленной из этих векторов как столбцов:

$$
\Delta V_x = |\det(\vec{v}_1, \vec{v}_2, ..., \vec{v}_n)| = |\det(J_{\mathbf{F}})| \cdot \Delta u_1 \Delta u_2 \cdots \Delta u_n
$$

Но $\det(J_{\mathbf{F}})$ — это якобиан $J$, а $\Delta u_1 \Delta u_2 \cdots \Delta u_n = \Delta V_u$, поэтому:

$$
\Delta V_x = |J| \cdot \Delta V_u
$$

### Полярные координаты

---

$$
x = r\cos\theta, \quad y = r\sin\theta
$$

Матрица Якоби:

$$
J = \frac{\partial(x,y)}{\partial(r,\theta)} = 
\begin{pmatrix}
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta} \\ 
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta}
\end{pmatrix}
= 
\begin{pmatrix}
\cos\theta & -r\sin\theta \\
\sin\theta & r\cos\theta
\end{pmatrix}
$$

Якобиан:

$$
J = \det(J) = \cos\theta \cdot r\cos\theta - (-r\sin\theta) \cdot \sin\theta = r\cos^2\theta + r\sin^2\theta = r
$$

Таким образом, при переходе к полярным координатам:

$$
dxdy = |J|drd\theta = rdrd\theta
$$

### Цилиндрические координаты

---

$$
\begin{cases}
x = \rho \cos\varphi \\
y = \rho \sin\varphi \\
z = z
\end{cases}
$$

где:
- $\rho \geq 0$ — расстояние до точки
- $0 \leq \varphi < 2\pi$ — угол в плоскости $XY$
- $z \in \mathbb{R}$ — высота

#### Матрица Якоби
Вычислим частные производные:

$$
\frac{\partial x}{\partial \rho} = \cos\varphi, \quad
\frac{\partial x}{\partial \varphi} = -\rho \sin\varphi, \quad
\frac{\partial x}{\partial z} = 0
$$

$$
\frac{\partial y}{\partial \rho} = \sin\varphi, \quad
\frac{\partial y}{\partial \varphi} = \rho \cos\varphi, \quad
\frac{\partial y}{\partial z} = 0
$$

$$
\frac{\partial z}{\partial \rho} = 0, \quad
\frac{\partial z}{\partial \varphi} = 0, \quad
\frac{\partial z}{\partial z} = 1
$$

$$
J = \frac{\partial(x,y,z)}{\partial(\rho,\varphi,z)} = 
\begin{pmatrix}
\cos\varphi & -\rho \sin\varphi & 0 \\
\sin\varphi & \rho \cos\varphi & 0 \\
0 & 0 & 1
\end{pmatrix}
$$

#### Якобиан
Вычислим определитель:

$$
\det(J) = 1 \cdot \begin{vmatrix}
\cos\theta & -r\sin\theta \\
\sin\theta & r\cos\theta
\end{vmatrix} = r
$$

Тогда:

$$
dxdydz = |J| d\rho d\varphi dz = \rho d\rho d\varphi dz
$$

### Сферические координаты

---

$$
\begin{cases}
x = r \sin\theta \cos\varphi \\
y = r \sin\theta \sin\varphi \\
z = r \cos\theta
\end{cases}
$$
где:
- $r \geq 0$ — расстояние до точки
- $0 \leq \theta \leq \pi$ —  угол от оси $Z$
- $0 \leq \varphi < 2\pi$ — угол в плоскости $XY$
  
#### Матрица Якоби

Вычислим частные производные:

$$
\frac{\partial x}{\partial r} = \sin\theta \cos\varphi, \quad
\frac{\partial x}{\partial \theta} = r \cos\theta \cos\varphi, \quad
\frac{\partial x}{\partial \varphi} = -r \sin\theta \sin\varphi
$$

$$
\frac{\partial y}{\partial r} = \sin\theta \sin\varphi, \quad
\frac{\partial y}{\partial \theta} = r \cos\theta \sin\varphi, \quad
\frac{\partial y}{\partial \varphi} = r \sin\theta \cos\varphi
$$

$$
\frac{\partial z}{\partial r} = \cos\theta, \quad
\frac{\partial z}{\partial \theta} = -r \sin\theta, \quad
\frac{\partial z}{\partial \varphi} = 0
$$

$$
J = \frac{\partial(x,y,z)}{\partial(r,\theta,\varphi)} = 
\begin{pmatrix}
\sin\theta \cos\varphi & r \cos\theta \cos\varphi & -r \sin\theta \sin\varphi \\
\sin\theta \sin\varphi & r \cos\theta \sin\varphi & r \sin\theta \cos\varphi \\
\cos\theta & -r \sin\theta & 0
\end{pmatrix}
$$

#### Якобиан

$$
\det(J) = r^2 \sin\theta
$$

Ну сами пересчитайте если не верите $:)$

$$
dxdydz = |J| dr d\theta d\varphi = r^2 \sin\theta dr d\theta d\varphi
$$