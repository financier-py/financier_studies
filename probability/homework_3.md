# Домашняя работа

## Задание 1

Введем след. обозначения:

- червы: $w_1$
- бубны: $w_2$
- пики: $w_3$
- трефы: $w_4$

Тогда:

$$
\Omega = \set{w_1, w_2, w_3, w_4}
$$

$$
\mathcal{F} = \set{\emptyset, \set{w_1}, \set{w_2}, \set{w_3, w_4}, \set{w_1, w_2}, \set{w_1, w_3, w_4}, \set{w_2, w_3, w_4}, \Omega}
$$

Окей, будем пользоваться этим:

[![image](https://b.fotohosting.pro/2025/12/02/imagec6f62d012adda173.png)](https://fotohosting.pro/i/image.JeIbJ)

Тк у нас ф-ии с конечным числом значений $\set{a_k}$, то:

$$
f^{-1}(B) = \bigcup_{a_k \in B} f^{-1}(\set{a_k})
$$

Поэтому достаточно будет проверить прообразы одноточечных мн-в для определения измеримости $:)$

Начнем с $\xi$:

$$
\xi^{-1}(\{1\})=\{w_1\}\in\mathcal F,\quad
\xi^{-1}(\{2\})=\{w_2\}\in\mathcal F,\quad
\xi^{-1}(\{3\})=\{w_3,w_4\}\in\mathcal F
$$

Отсюда вывод, что $\xi$ измеримая!

Теперь разберемся с $\eta$:

$$
\eta^{-1}(\{2\})=\{w_3\} \notin \mathcal{F}
$$

Поэтому она неизмеримая!

Ответ: изм., неизм.

## Задание 2

Пусть $B \in \mathcal{B}(\R)$

Если $a \in B$, тогда $\xi(w) \in B \ \forall w \in \Omega$. Поэтому:

$$
\xi^{-1}(B) = \Omega \in \mathcal{F}
$$

А если $a \notin B$, тогда:

$$
\xi^{-1}(B) = \emptyset \in \mathcal{F}
$$

Поэтому по опред. ф-ия измеримая

Ответ: измеримая

## Задание 3

Сначала докажем достаточность. Как мы поняли из прошлого задания, постоянная ф-ия измерима относительно любой сигма алгебры, поэтому и для $\mathcal{F} = \set{\Omega, \empty}$ она будет измерима. доказано $:)$

Докажем необходимость теперь. У нас есть $\xi : \Omega \to \R$ и $\mathcal{F} = \set{\Omega, \empty}$ и $\xi$ является измеримой относительно $\mathcal{F}$

От противного. $\exists w_1, w_2 \in \Omega : \xi(w_1) \neq \xi(w_2)$. Обозначим $a = \xi(w_1)$. Мн-во $\set{a} \subset \R$ и является борелевским, поэтому:

$$
\xi^{-1}(\set{a}) = \set{w \in \Omega : \xi(w) = a}
$$

Но мы знаем, что $\xi^{-1}(\set{a}) \neq \empty$, так как, как минимум, $w_1 \in \xi^{-1}(\set{a})$, но и $\xi^{-1}(\set{a}) \neq \Omega$, так как $w_2 \notin \xi^{-1}(\set{a})$, ибо $a \neq \xi(w_2)$

Поэтому получаем, что $\xi^{-1}(\set{a}) \notin \mathcal{F}$, противоречие!

доказано $:)$

## Задание 4

### пункт а

$$
\xi_+(w) = \max(\xi(w), 0)
$$

Рассм. ф-ию $g(x) = \max(x, 0)$. Она у нас непрерывная, поэтому является борелевско измеримой. Можно посмотреть на график. _(вообще она является измеримой, так как у непрерывной функции прообраз любого открытого множества открыт, а борелевская сигма алгебра порождается всеми открытыми мн-ми, вот и все)_

[![image](https://b.fotohosting.pro/2025/12/02/image1441db3bbfb9b4d6.png)](https://fotohosting.pro/i/image.JiAI4)

Окей, супер. Теперь заметим, что $\xi_1(w) = g(\xi(w))$. Тогда для любого $B \in \mathcal{B}(\R)$ будет выполняться:

$$
\xi^{-1}_+(B) = \xi^{-1}(g^{-1}(B))
$$

Но тк $g$ измерима, то $g^{-1}(B)$ - борелевское мн-во. А так как $\xi$ измерима относительно $\mathcal F$, то получаем, что $\xi^{-1}(g^{-1}(B)) \in \mathcal F$

чтд

### пункт б

Для этого пункта все то же самое $:)$. Только вводим $g$ как $g = -\min(x, 0)$. Все остальные рассуждения аналогичны.

## Задача 5

Вспомним, что:

[![image](https://b.fotohosting.pro/2025/12/02/imagea3895a832145da33.png)](https://fotohosting.pro/i/image.Jo24g)

Окей, пусть у нас есть $m \in \N$, тогда:

$$
\mathbb{E}[X (X-1)\dots(X-m+1)] = \sum_{k = 1}^\infty k (k - 1) \dots (k - m + 1) \cdot P(X = k)
$$

$$
\mathbb{E}[X (X-1)\dots(X-m+1)] = \sum_{k = 1}^\infty k (k - 1) \dots (k - m + 1) \cdot \frac{\lambda^k}{k!}e^{-\lambda}
$$

Заметим, что при $k < m$ у нас в скобочках где-то обязательно возникнет нолик и все занулит, поэтому:

$$
\mathbb{E}[X (X-1)\dots(X-m+1)] = \sum_{k = m}^\infty k (k - 1) \dots (k - m + 1) \cdot \frac{\lambda^k}{k!}e^{-\lambda}
$$

Или

$$
\mathbb{E}[X (X-1)\dots(X-m+1)] = e^{-\lambda}\sum_{k = m}^\infty \frac{k!}{(k - m)!} \cdot \frac{\lambda^k}{k!}
$$

$$
\mathbb{E}[X (X-1)\dots(X-m+1)] = e^{-\lambda}\sum_{k = m}^\infty \frac{\lambda^k}{(k - m)!} 
$$

Пусть $j = k - m$, тогда:

$$
\mathbb{E}[X (X-1)\dots(X-m+1)] = e^{- \lambda} \sum_{j = 0}^\infty \frac{\lambda^{j + m}}{j!}
$$

По итогу получаем:

$$
\mathbb{E}[X (X-1)\dots(X-m+1)] = e^{- \lambda} \cdot \lambda^m \sum_{j = 0}^\infty \frac{\lambda^j}{j!}
$$

Пользуемся подсказочкой $:)$ и выходит:

$$
\mathbb{E}[X (X-1)\dots(X-m+1)] = e^{- \lambda} \cdot \lambda^m \cdot e^\lambda = \lambda^m
$$

Пользуясь этим, получаем:

### пункт а

$$
\mathbb{E}[X] = \lambda
$$

### пункт б

$$
\mathbb{E}[X(X-1)] = \lambda^2
$$

### пункт с

$$
\mathbb{E}[X^2] = \mathbb{E}[X(X - 1) + X] = \mathbb{E}[X(X- 1)] + \mathbb{E}[X] = \lambda^2 + \lambda
$$

### пункт д

$$
\mathbb{E}[X(X-1)(X-2)] = \lambda^3
$$

### пункт е

$$
X(X-1)(X-2) = X^3 - 3X^2 - 2X
$$

Тогда

$$
X^3 = X(X-1)(X-2) + 3X(X - 1) + 3X - 2X
$$

Получим:

$$
\mathbb{E}[X^3] = \mathbb{E}[X(X-1)(X-2)] +3 \mathbb{E}[X(X - 1)] + \mathbb{E}[X] = \lambda^3 +3\lambda^2 + \lambda
$$

### пункт эф

$$
\mathbb{E}[X(X-1)(X-2)(X-3)] = \lambda^4
$$

### пункт жэ

$$
X(X-1)(X-2)(X-3) = X^4 -6X^3 +11X^2 -6X
$$

Тогда:

$$
X^4 =  X(X-1)(X-2)(X-3) + 6X(X-1)(X-2) + 
$$

$$
+ 18X(X - 1) +6X -11X(X - 1) -11 X + 6X
$$

$$
=  X(X-1)(X-2)(X-3) + 6X(X-1)(X-2) + 7X(X - 1) + X
$$

Тогда:

$$
\mathbb{E}[X^4] = \mathbb{E}[X(X-1)(X-2)(X-3)] + 6 \mathbb{E}[X(X-1)(X-2)] +
$$

$$
+ 7 \mathbb{E}[X(X - 1)] + \mathbb{E}[X] =
$$

$$
= \lambda^4 + 6 \lambda^3 + 7 \lambda^2 + \lambda
$$

Ответ: ответы написаны под каждым пунктом