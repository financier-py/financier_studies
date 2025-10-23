# Домашняя работа

## Задача 1

$$
\sum_{n = 1}^{\infty} \frac{n}{(4n^2 - 1)^2} \Rightarrow a_n = \frac{n}{(4n^2 - 1)^2}
$$

$$
a_n = \frac{n}{(2n - 1)^2(2n + 1)^2} = \frac{A}{(2n - 1)^2} + \frac{B}{(2n + 1)^2}
$$

$$
\Rightarrow A(2n + 1)^2 + B(2n - 1)^2 = n
$$

$$
A4n^2 + A4n + A + B4n^2 -B4n + B - n = 0 
$$

$$
n^2(A4 + B4) + n(A4 - B4 - 1) + (A + B) = 0
$$

Тогда получаем:

$$
\begin{equation*}
    \begin{cases}
        A + B = 0 \\
        A - B = \frac{1}{4}
    \end{cases}
\end{equation*} \Rightarrow 

\begin{equation*}
    \begin{cases}
        A = -B \\
        -2B = \frac{1}{4}
    \end{cases}
\end{equation*} \Rightarrow

\begin{equation*}
    \begin{cases}
        B = - \frac{1}{8} \\
        A = \frac{1}{8}
    \end{cases}    
\end{equation*}
$$

Окей, тогда получим:

$$
a_n = \frac{1}{8} \left(\frac{1}{(2n - 1)^2} - \frac{1}{(2n + 1)^2} \right)
$$

Теперь рассмотрим част. суммы или как их там:

$$
S_N = \sum_{n = 1}^N \frac{1}{8} \left(\frac{1}{(2n - 1)^2} - \frac{1}{(2n + 1)^2} \right) = 
$$

$$
= \frac{1}{8} \left[ \left(\frac{1}{1^2} - \frac{1}{3^2} \right) + \left(\frac{1}{3^2} - \frac{1}{5^2} \right) + \left(\frac{1}{5^2} - \frac{1}{7^2} \right) + \dots \right]
$$

Видим, что эт телескопическая сумма ну и догадаемся, что:

$$
8 \cdot S_N = 1 - \frac{1}{N^2}
$$

Тк нам нужно найти сумму ряда, то ей будет равен этот предел:

$$
\lim_{n \to \infty} S_n = \frac 1 8  - \frac 1 8\lim_{n \to \infty} \frac{1}{n^2} = 8
$$

Ответ: $\frac 1 8$

## Задача 2

### a)

$$
\sum_{n = 1}^{\infty} \left(1 - \frac{1}{n} \right)^n \Rightarrow a_n = \left(1 - \frac{1}{n} \right)^n
$$

Посмотрим на необход. условие сход. ряда:

$$
\lim_{n \to \infty} \left(1 - \frac{1}{n} \right)^n = e^{-1} \neq 0
$$

$$
\Rightarrow \text{не сходится кайф}
$$

Ответ: нет

### b)

$$
\sum_{n = 1}^{\infty} n \sin \left(\frac{n + 1}{n^2 + 2} \right) \Rightarrow a_n = n \sin \left(\frac{n + 1}{n^2 + 2} \right)
$$

Пусть $t = \frac{n + 1}{n^2 + 2}$, тогда $a_n = n \sin t = tn \frac{\sin t}{t}$

$$
\text{при } n \to \infty : \ \frac{n + 1}{n^2 + 2} \to 0 \Rightarrow t \to 0 \Rightarrow \frac{\sin t}{t} \to 1
$$

Теперь посмотрим на необход. условие сход. ряда:

$$
\lim_{n \to \infty} a_n = \lim_{n \to \infty} \frac{n^2 + n}{n^2 + 2} \cdot \lim_{n \to \infty} \frac{\sin t}{t} = 1 \neq 0 \Rightarrow \text{ряд не сход. ура!}
$$

Ответ: нет

### d)

$$
\sum_{n = 2}^{\infty} \frac{\ln n + 3}{n (\ln^2 n + 2)} \Rightarrow a_n = \frac{\ln n + 3}{n (\ln^2 n + 2)}
$$

Рассмотрим ф-ию:

$$
f(x) = \frac{\ln x}{x \ln^2 x } = \frac{1}{x \ln x}
$$

$$
f'(x) = \frac{- \ln x - 1}{x^2 \ln^2 x} < 0 \ \  \forall x > 1 
$$

Будем пользоваться этим короче, посмотрим на ряд: $\sum_{i = 2}^{\infty} \frac{1}{i \ln i}$ и проверим его сходимость *(и $b_n = \frac{1}{ n\ln n}$)*

[![image](https://b.fotohosting.pro/2025/10/19/imagef1c7fd8c917ba458.png)](https://fotohosting.pro/i/image.WsepL)

Тогда вычислим интеграл:

$$
\int_2^\infty \frac{1}{x \ln x} dx = \lim_{b \to \infty} \int_2^b \frac{dx}{x \ln x}
$$

Пусть $u = \ln x$, тогда $du = \frac{dx}{x}$:

$$
\lim_{b \to \infty} \int_{\ln 2}^{\ln b} \frac{du}{u} = \lim_{b \to \infty} \ln(\ln b) - \ln(\ln 2) = \infty
$$

$$
\Rightarrow \text{интеграл расходится}
$$

$$
\Rightarrow \text{ряд тогда тоже расходится}
$$

Теперь рассмотрим такой вот предел:

$$
\lim_{n \to \infty} \frac{a_n}{b_n} = \lim_{n \to \infty} \frac{n\ln^2 n + 3n \ln n}{n (\ln^2 n + 2)} = \lim_{n \to \infty} \frac{n \ln^2 n}{n \ln^2 n + 2n} + \lim_{n \to \infty} \frac{3n \ln n }{n \ln^2 n + 2n} = 
$$

$$
= \lim_{n \to \infin} \frac{\ln^2 n }{\ln^2 n + 2} + \lim_{n \to \infty} \frac{3 \ln n}{\ln^2 n + 2} = 1 + 0 = 1
$$

$$
\Rightarrow a_n \sim b_n \Rightarrow \sum_{n = 2}^\infin a_n \sim \sum_{n = 2}^\infin b_n
$$

Поэтому наш изначальный ряд расходится!

Пользовался этим выше:

[![image](https://a.fotohosting.pro/2025/10/19/image021985bd762d3f97.png)](https://fotohosting.pro/i/image.WsF2t)

Ответ: расход пацаны

### f)

$$
\sum_{n = 1}^{\infty} \frac{(n!)^2}{(2n)!} \Rightarrow a_n = \frac{(n!)^2}{(2n)!} 
$$ 

Попробуем Даламбергом, рассмотрим:

$$
\frac{a_{n + 1}}{a_n} = \frac{((n + 1)!)^2 \cdot (2n)!}{(2n + 2)! \cdot (n!)^2} = \frac{(n + 1)^2}{(2n + 1)(2n + 2)} = \frac{n^2 + 2n + 1}{4n^2 + 6n + 2}
$$

$$
\Rightarrow \lim_{n \to \infty} \frac{a_{n + 1}}{a_n} = \lim_{n \to \infty} \frac{n^2 + 2n + 1}{4n^2 + 6n + 2} = \frac{1}{4} < 1 \Rightarrow \text{ряд сходится ура}
$$

Ответ: сходка ребята

### g) 

$$
\sum_{n = 1}^{\infty} \arctg^n \frac{\sqrt{3n + 1}}{\sqrt{n + 2}} \Rightarrow a_n = \arctg^n \frac{\sqrt{3n + 1}}{\sqrt{n + 2}}
$$

По рад. Коши попробуем:

$$
\sqrt[n]{a_n} = \arctg{\sqrt{\frac{3n + 1}{n + 2}}}
$$

Рассм. предел:

$$
\lim_{n \to \infty} \sqrt[n]{a_n} = \lim_{n \to \infty} \arctg{\sqrt{3}} = \frac{\pi}{3} > 1 \Rightarrow \text{ряд расход.}
$$

Ответ: расход

### h)

$$
\sum_{n = 1}^{\infty} \frac{(2n + 3)!!}{n^3(2n)!!} \Rightarrow a_n = \frac{(2n + 3)!!}{n^3(2n)!!} 
$$

Попробуем Даламбергом:

$$
\frac{a_{n + 1}}{a_n} = \frac{(2n + 5)!! \cdot n^3 (2n)!!}{(n + 1)^3 (2n + 2)!! \cdot (2n + 3)!!} = \frac{(2n + 3)!! \cdot (2n + 5) \cdot (2n)!! \cdot n^3}{(2n)!! \cdot (2n + 2) \cdot (2n + 3)!! \cdot (n + 1)^3} =
$$

$$
= \frac{(2n + 5)n^3}{(2n + 2)(n + 1)^3} \to 1 \text{ при } n \to \infty 
$$

К сожалению, не фортануло 

$$
(2n)!! = 2 \cdot 4 \cdot 6 \cdot \dotsc \cdot (2n - 2) \cdot 2n = 2^n \cdot (1 \cdot 2 \cdot 3 \dotsc \cdot (n - 1) \cdot n) = 2^n n !
$$

$$
(2n + 1)!! = 1 \cdot 3 \cdot 5 \cdot 7 \cdot \dotsc \cdot (2n - 1) \cdot (2n + 1) = \frac{(2n + 1)!}{2^n n!}
$$

Тогда:

$$
a_n = \frac{(2n + 3)(2n + 1)!}{n^3 \cdot 4^n \cdot (n!)^2}
$$

Теперь рассмотрим:

$$
n! = 1 \cdot 2 \cdot 3 \dotsc \cdot (n - 1) \cdot n
$$

Тогда:

$$
\ln(n!) = \ln(1 \cdot 2 \cdot 3 \dotsc \cdot (n - 1) \cdot n) = \ln1 + \ln2 + \dotsc + \ln n = \sum_{k = 1}^{n} \ln k
$$

Покажу теперь, что $\int_1^n \ln x dx \leq \sum_{k = 1}^n \ln k \leq \int_1^n \ln x dx + \ln n$

Типо верхняя как и нижняя оценка просто следует из опред. интеграла, но вот пояснение: на каждом отрезке $[k, k+1]$, $\forall k \in \set{1, 2, \dotsc, n-1}$, $\ln k \leq \int_k^{k + 1} \ln x dx$ просто из-за монотонного возрастания, суммируя по всем $k$ получим: $\sum_{k = 1}^{n - 1} \ln k \leq \int_1^n \ln x dx$, к обоим частям просто прибавим $\ln n$ и получим верхнюю оценку:

$$
\sum_{k = 1}^n \ln k \leq \int_1^n \ln x dx + \ln n \text{ - доказано}
$$

Теперь разберемся с нижней. По опреду интеграла понятно, что на каждом отрезке $[k, k+1]$ $\int_k^{k + 1} \ln x dx \leq \ln(k + 1)$, просто просуммируем и получим нижнюю оценку:

$$
\int_1^n \ln x dx \leq \sum_{k = 1}^n \ln k \text{ - доказано}
$$

Ладно, теперь посчитаем сам интеграл:

$$
\int_1^n \ln x dx = [x \ln x - x]_1^n = n \ln n - n + 1
$$

Теперь рассмотрим предел:

$$
\lim_{n \to \infty} \frac{\ln (n!)}{n \ln n - n + 1} 
$$

Из наших оценок получим, что:

$$
1 \leq \frac{\ln (n!)}{n \ln n - n + 1} \leq 1 + \frac{\ln n}{n \ln n - n + 1}
$$

Очевидно, что при $n \to \infty :$ $\frac{\ln n}{n \ln n - n + 1} \to 0$, поэтому мы зажали предел изначальный по сути и поэтому:

$$
\lim_{n \to \infty} \frac{\ln (n!)}{n \ln n - n + 1} = 1
$$

что показывает, что:

$$
\ln(n!) \sim n \ln n - n + 1 \text{ при } n \to \infty
$$

При $n \to \infty :$ $n \ln n - n + 1 \sim n \ln n - n$

Теперь можем возвести все в экспоненту и тогда получим, что:

$$
n! \sim n^n \cdot e^{-n} \text{ при } n \to \infty
$$

короче как я понял тут нельзя возводить в экспоненту поэтому я хз как решать _(типо эквивалентность не сохраняется)_

Рассмотрим заново:

$$
a_n = \frac{(2n + 3) \cdot 1 \cdot 2 \cdot 3 \cdot \dotsc \cdot 2n \cdot (2n + 1)}{n^3 \cdot 4^n \cdot 1^2 \cdot 2^2 \cdot (n - 1)^2 \cdot n^2} = 
$$

$$
= \frac{(2n + 3) \cdot (n + 1) \cdot (n + 2) \cdot \dotsc \cdot 2n \cdot (2n + 1)}{n^3 \cdot 4^n \cdot n!}
$$

хз крч

Мне подсказали, что есть ф-ла Стирлинга:

$$
n! \sim \sqrt{2 \pi n} \cdot n^n \cdot e^{-n} \sim \sqrt{n} \cdot n^n \cdot e^{-n}
$$

Поэтому $a_n$ эквивалентна:

$$
b_n = \frac{(2n + 3) \cdot \sqrt{2n + 1} \cdot (2n + 1)^{2n + 1} \cdot e^{-2n - 1}}{n^3 \cdot 4^n \cdot n \cdot n^{2n} \cdot e^{-2n}} = e^{-1} (2n + 3) \cdot \frac{(2n + 1)^{2n + \frac{3}{2}}}{4^n \cdot n^{2n + 4}} 
$$

$$
b_n \sim n \cdot \frac{4^n \cdot n^{2n} \cdot n^{\frac{3}{2}}}{4^n \cdot n^{2n} \cdot n^4} = \frac{1}{n^{\frac{3}{2}}}
$$

$$
\sum_{n = 1}^\infty \frac{1}{n^{\frac{3}{2}}} \sim \sum_{n = 1}^{\infty} \frac{(2n + 3)!!}{n^3(2n)!!} 
$$

А ряд $\sum_{n = 1}^\infty \frac{1}{n^{\frac{3}{2}}}$ сходится, так как $\frac{3}{2} > 1$

Ответ: сходится

## Задача 3

### a)

$$
\sum_{n = 1}^{\infty} \frac{(-1)^n \sqrt{n}}{3n - 2} \Rightarrow a_n = \frac{(-1)^n \sqrt{n}}{3n - 2}
$$

Рассмотрим $b_n = \frac{\sqrt{n}}{3n - 2}$

$$
\lim_{n \to \infty} b_n = \lim_{n \to \infty} \frac{n^\frac{1}{2}}{3n - 2} = 0
$$

Теперь докажем, что $b_{n + 1} < b_n$:

$$
\frac{\sqrt{n + 1}}{3n + 1} < \frac{\sqrt{n}}{3n - 2}
$$

$$
\sqrt{n + 1} \cdot (3n - 2) < \sqrt{n} \cdot (3n + 1)
$$

$$
(n + 1)(3n - 2)^2 < n \cdot (3n + 1)
$$

$$
-9n^2 - 9n + 4 < 0
$$

Ну тут очевидно становится, что $\forall n \in \mathbb{N}$ это истина 

Поэтому доказали, что $b_n$ монотонно убывает

Тогда по Лейбницу $a_n$ сходится

Ответ: сход

### b)

$$
\sum_{n = 1}^{\infty} \frac{\cos n}{n + \ln n}
$$

Пусть $a_n = \cos n$, и $b_n = \frac{1}{n + \ln n}$

Очев:

$$
\lim_{n \to \infty} b_n = \lim_{n \to \infty} \frac{1}{n + \ln n} = 0
$$

Тк $n + \ln n$ - это монотонно возрастающая ф-ия, хз если не очев могу расписать $\Rightarrow$ $b_n$ монотонно убывает

$$
b_n < b_{n + 1}
$$

$$
n + \ln n < n + 1 + \ln(n + 1)
$$

$$
\ln n < \ln(n + 1) + 1
$$

$$
\ln n < \ln(n + 1) + \ln e
$$

$$
\ln n < \ln(en + e)
$$

$$
n < en + e
$$

$$
n (1 - e) < e
$$

$$
n > \frac{e}{1 - e}
$$

Понимаем, что $\frac{e}{1 - e} < 0$, поэтому для $\forall n \in \mathbb{N}$ наше неравенство верно !

Да мне нечего делать, будет забавно если я там сделал ошибки, я прямо кекну

Теперь короче посмотрим на эту тему:

$$
\sum_{n = 1}^N \cos n = \frac{\sin(N + \frac{1}{2}) - \sin\frac{1}{2}}{2 \sin \frac{1}{2}}
$$

Поэтому можем оценить:

$$
\bigg| \sum_{n = 1}^N \cos n \bigg| = \frac{|\sin(N + \frac{1}{2}) - \sin\frac{1}{2} |}{2 \sin \frac{1}{2}} \leq \frac{1 + 1}{2 \sin \frac{1}{2}} = \frac{1}{\sin \frac{1}{2}}
$$

Ну вот константной оценили 

Поэтому ряд $\sum_{n = 1}^{\infty} a_n \cdot b_n$ сходится, а это наш изначальный ряд!

Ответ: сходится

### c)

$$
\sum_{n = 1}^{\infty} \frac{(-1)^{[\ln n]}}{2^n + n} \Rightarrow a_n = \frac{(-1)^{[\ln n]}}{2^n + n} 
$$

$|a_n| = \frac{1}{2^n + n}$

$$
\frac{1}{2^n + n} < \frac{1}{2^n} \ \forall n \in \mathbb{N}
$$

А ряд $\sum_{n = 1}^{\infty} \frac{1}{2^n}$ сходится так как это по сути геом прогрессия

Тогда и ряд $\sum_{n = 1}^{\infty} |a_n|$ сходится, а значит $a_n$ сходится абсолютно ну значит и по обычному он сходится

Ответ: сходится 

### d)

$$
\sum_{n = 1}^{\infty} \frac{(-1)^n \sin 2n}{\sqrt{n + 6}}
$$

Пусть $a_n = \frac{1}{\sqrt{n + 6}}$ и она монотонно убывает к нулю, что очев

И пусть $b_n = (-1)^n \sin 2n = \cos(\pi n) \sin(2n) = \frac{1}{2}(\sin(n \pi + 2n) - \sin(n \pi - 2n))$

Поэтому:

$$
\sum_{n = 1}^N b_n = \frac{1}{2} \sum_{n = 1}^N \sin(n(\pi + 2)) - \frac{1}{2} \sum_{n = 1}^{\infty} \sin(n (\pi - 2))
$$

И можем это расписать по этой формуле:

$$
\sum_{n = 1}^N \sin(\alpha n) = \frac{\sin(\frac{\alpha N}{2}) \sin(\frac{\alpha (N + 1)}{2})}{\sin(\frac{\alpha}{2})}
$$

В нашем случае $|\sin(\frac{\alpha N}{2}) \sin(\frac{\alpha (N + 1)}{2})|$ мы оценим сверху единицей.

$$
\sin \left(\frac{\pi + 2}{2} \right) = \sin \left(\frac{\pi}{2} + 1 \right) = \cos 1
$$

И аналогично для второго ряда посчитаем знаменатель $:)$

$$
\sin \left(\frac{\pi - 2}{2} \right) = \sin \left(\frac{\pi}{2} - 1 \right) = \cos 1
$$

Поэтому:

$$
\sum_{n = 1}^N b_n \leq \frac{1}{2} \cdot \frac{1}{\cos 1} \cdot (1 + 1) = \frac{1}{\cos 1}
$$

Тогда по Дирихле ряд сходится!

Ответ: сходится

### e)

$$
\sum_{n = 1}^{\infty} \frac{\sin(n + \frac{\pi}{3})}{\ln(n^2 + 3)} \cdot e^{\frac{n + 1}{n}}
$$

Пусть $a_n = \frac{e^{\frac{1}{n}} \cdot e}{\ln(n^2 + 3)}$, $\ b_n = \sin(n + \frac{\pi}{3})$

$$
\lim_{n \to \infty} a_n = \lim_{n \to \infty} \frac{e^{\frac{1}{n}} \cdot e}{\ln(n^2 + 3)} = 0
$$

Теперь попробуем доказать, что $a_n$ монотонно убывает:

$$
\frac{a_{n+1}}{a_n} = \frac{e \cdot e^{\frac{1}{n + 1}} \cdot \ln(n^2 + 3)}{\ln((n+ 1)^2 + 3) \cdot e \cdot e^\frac{1}{n}} = e^{-\frac{1}{n(n + 1)}} \cdot \frac{\ln(n ^ 2 + 3)}{\ln((n+ 1)^2 + 3)}
$$

Очев, что $\forall n > 0: 0 < e^{-\frac{1}{n(n + 1)}} < 1$

Также очев, что $\forall n > 0: n^2 + 3 < (n + 1)^2 + 3$

Поэтому $\ln((n + 1)^2 + 3) > \ln(n^2 + 3) \Rightarrow \frac{\ln(n ^ 2 + 3)}{\ln((n+ 1)^2 + 3)} < 0$

$$
\Rightarrow e^{-\frac{1}{n(n + 1)}} \cdot \frac{\ln(n ^ 2 + 3)}{\ln((n+ 1)^2 + 3)} < 0 \Rightarrow a_{n + 1} < a_n
$$

чтд

Теперь распишем $b_n$ по ф-ле синуса суммы:

$$
b_n = \sin \left(n + \frac{\pi}{3} \right) = \frac{1}{2} \sin n + \frac{\sqrt{3}}{2} \cos n
$$

Теперь посмотрим на частичные суммы $b_n$:

$$
\sum_{n = 1}^N b_n = \frac 1 2 \sum_{n = 1}^N \sin n + \frac{\sqrt{3}}{2} \sum_{n = 1}^N \cos n 
$$

Как мы выше видели, есть закрытые формулы для рядов синуса и косинуса и мы их уже оценивали сверху, поэтому очев, что $|b_n| < M$, где $M$ - константа

$\Rightarrow$ по Дирихле ряд сходится $:)$

Ответ: сходится!