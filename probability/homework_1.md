# Домашняя работа

## Задача 1

Вспомним определения из дискретной математики:

$$
A \setminus B = \set{x \mid x \in A \land x \notin B}
$$

$$
A \Delta B = A \setminus B \cup B \setminus A = \set{x \mid x \in A \land x \notin B \lor x \in B \land x \notin A}
$$

$$
A \cap B = \set{x \mid x \in A \land x \in B}
$$

Окей, теперь докажем:

$$
A \setminus B = (A \Delta B) \cap A
$$

Пусть $x \in A \setminus B$, тогда $x \in A \land x \notin B$. По опред. симм. разности: $A \Delta B = A \setminus B \cup B \setminus A$, тогда т.к. $x \in A \setminus B$, то $x \in A \Delta B$!

Выходит, что наш $x$ лежит и в $A$ и в $A \Delta B$, что значит, что $x \in A \cap (A \Delta B)$.

Доказали, что $A \setminus B \subseteq A \cap (A \Delta B)$!

Пусть теперь $x \in (A \Delta B) \cap A$, что значит, что $x \in A$ и $x \in A \Delta B$. По опред. симм. разности: $A \Delta B = A \setminus B \cup B \setminus A$.

Если наш $x$ лежит в $B \setminus A$, то это значит, что $x \in B \land x \notin A$, но так как $x \in A$, то такого не может быть. 

Выходит, остается только, что $x \in A \setminus B$, что значит $x \in A \land x \notin B$, что согласуется с условием $x \in A$

Следовательно, $(A \Delta B) \cap A \subseteq A \setminus B$

чтд

## Задача 2

Докажем, что $A \cup B = (A \Delta B) \Delta (A \cap B)$

Пусть $x \in A \cup B$, тогда $x \in A \lor x \in B$. Рассмотрим два случая:

Если $x \in A \cap B$, тогда $x \in A \land x \in B$. Так как $x \in A \cap B$, то $x \notin A \Delta B$. Тогда $x \in (A \cap B) \setminus (A \Delta B)$. Выходит, что тогда $x \in (A \Delta B) \Delta (A \cap B)$ по опреду симм. разности

Если же $x \notin A \cap B$, тогда возможны два подслучая:

- $x \in A \land x \notin B$, то тогда $x \in A \setminus B \subseteq A \Delta B$ 
- $x \in B \land x \notin B$, то тогда $x \in B \setminus A \subseteq A \Delta B$

Во всех подслучаях $x \in A \Delta B$ и при этом $x \notin A \cap B$, тогда $x \in (A \Delta B) \setminus (A \cap B)$, что по опред. симм. разности значит, что $x \in (A \Delta B) \Delta (A \cap B)$!

Следовательно, $A \cup B \subseteq (A \Delta B) \Delta (A \cap B)$.

Теперь пусть $x \in (A \Delta B) \Delta (A \cap B)$, что значит, что $x \in (A \Delta B) \setminus (A \cap B)$ или $x \in (A \cap B) \setminus (A \Delta B)$. Рассмотрим эти два случая:

- $x \in A \Delta B \land x \notin A \cap B$, тогда $x \in A \setminus B$ или $x \in B \setminus A$, что значит $x \in A \cup B$!

- $x \in A \cap B \land x \notin A \Delta B$, что значит, что $x \in A \land x \in B$, откуда следует, что $x \in A \cup B$

Ну и тогда $(A \Delta B) \Delta (A \cap B) \subseteq A \cup B$

чтд

### Задача 3

Имеем беск. последовательность мн-в: $A_1, A_2, A_3, \dots, A_n, \dots$

Если $x \in \lim \sup A_n$, то это значит, что существуют $n_1, n_2, n_3, \dots$ такие, что $x \in A_{n_1}$ и $x \in A_{n_2}$ и $x \in A_{n_3}$ и т.д. и этих индексов бесконечность

Нам как-то нужно выразить через $\cap$ и $\cup$ все такие $x$

Попробуем рассмотреть объединение всех множеств:

$$
B_1 = A_1 \cup A_2 \cup A_3 \cup A_4 \cup \dots \cup A_n \cup \dots
$$

Но в $B_1$ есть и те элементы, которые появляются конечное количество раз. Попробуем убрать $A_1$ и посмотрим, что останется:

$$
B_2 = A_2 \cup A_3 \cup A_4 \cup \dots \cup A_n \cup \dots
$$

Если элемент был только в $A_1$, то в $B_2$ его уже не будет!

Уберем теперь и $A_2$:

$$
B_3 = A_3 \cup A_4 \cup \dots \cup A_n \cup \dots
$$

В $B_3$ уже не будет элементов, которые встретились только в $A_2$ и/или в $A_3$

Тут можем понять, что те элементы, которые встречаются бесконечное количество раз должны быть и в $B_1$ и в $B_2$ и в $B_3$ и так далее!

То есть сколько бы начальных множеств мы не отбросили, этот элемент всегда должен появляться в оставшейся части $:)$

То есть $\lim \sup A_n = \bigcap_{n=1}^{\infin} B_n$

Ну а $B_n$, как мы поняли, равен $\bigcup_{k = n}^{\infin} A_k$

Тогда:

$$
\lim \sup A_n = \bigcap_{n=1}^{\infin} \bigcup_{k = n}^{\infin} A_k
$$

Докажем, что это так:

Пусть:
$$
x \in \bigcap_{n=1}^{\infin} \bigcup_{k = n}^{\infin} A_k
$$

Что значит, что $\forall n \geq 1 \ x \in \bigcup_{k = n}^{\infin} A_k$

Пусть $x$ появился только конечное количество раз. Тогда существует какой-то номер множества, в котором он появился последний раз, то есть $\exist N : \forall k > N  \ x \notin A_k$

Рассмотрим тогда множество $\bigcup_{k = N + 1}^{\infin} A_k$. Согласно нашему предположению, $x \notin \bigcup_{k = N + 1}^{\infin} A_k$, но получаем противоречие с тем, что $x \in \bigcap_{n=1}^{\infin} \bigcup_{k = n}^{\infin} A_k$

Следовательно, $x$ встречается беск. кол-во раз, тогда $x \in \lim \sup A_n$! Ну и тогда:

$$
\bigcap_{n=1}^{\infin} \bigcup_{k = n}^{\infin} A_k \subseteq \lim \sup A_n
$$

Теперь пусть:

$$
x \in \lim \sup A_n
$$

Возьмем произвольный $m > 0$ и рассмотрим мн-во $\bigcup_{k = m}^{\infin} A_k$

Посколько $x \in \lim \sup A_n$, то $\exist N \geq m : x \in A_N$, что значит, что $x \in \bigcup_{k = m}^{\infin} A_k$

А так как это верно для любого $m > 0$, то $x$ должен принадлежать $\bigcap_{n=1}^{\infin} \bigcup_{k = n}^{\infin} A_k$

Следовательно:

$$
\lim \sup A_n \subseteq \bigcap_{n=1}^{\infin} \bigcup_{k = n}^{\infin} A_k
$$

чтд

### Задача 4

Имеем беск. последовательность мн-в: $A_1, A_2, A_3, \dots, A_n, \dots$

Если $x \in \lim \inf A_n$, то это значит, что существует $0$ или конечное число номеров $n_1, n_2, \dots n_k$ таких, что $x \notin A_{n_1}$ и $x \notin A_{n_2}$ и $\dots$ и $x \notin A_{n_k}$

Попробуем рассмотреть мн-во:

$$
B_1 = A_1 \cap A_2 \cap A_3 \cap A_4 \cap \dots \cap A_n \cap \dots
$$

$B_1$ включает в себя все элементы, которые принадлежат всем множествам последовательности, но в нем нет, например, тех элементов, которые бы принадлежали всем множествам последовательности, за исключением, например, одного или там двух или там трех. Логика понятна в общем

Тогда рассмотрим такое мн-во:

$$
B_2 = A_2 \cap A_3 \cap A_4 \cap \dots \cap A_n \cap \dots
$$

В $B_2$ есть все элементы, которые находятся во всех мн-вах послед-сти, кроме мн-ва $A_1$

Продолжим цикл:

$$
B_3 = A_3 \cap A_4 \cap \dots \cap A_n \cap \dots
$$

Тут понимаем, что $\lim \inf A_n = \bigcup_{n = 1}^{\infin} B_n$

Ну а $B_n$, как мы поняли ранее, равен $\bigcap_{k = n}^{\infin} B_k$

Тогда:

$$
\lim \inf A_n = \bigcup_{n = 1}^{\infin} \bigcap_{k = n}^{\infin} A_k
$$

Ну теперь докажем это:

Пусть $x \in \bigcup_{n = 1}^{\infin} \bigcap_{k = n}^{\infin} A_k$, тогда $\exist N > 0: x \in \bigcap_{k = N}^{\infin} A_k$, что по сути значит, что $x$ принадлежит бесконечному кол-ву мн-в послед-сти, кроме конечного числа, т.е. $x \in \lim \inf A_n$

Следовательно, $\bigcup_{n = 1}^{\infin} \bigcap_{k = n}^{\infin} A_k \subseteq \lim \inf A_n$

Пусть $x \in \lim \inf A_n$, значит $\exist N > 0 : \forall m \geq N \ x \in A_m$, то есть $x \in \bigcap_{k = N}^{\infin} A_k$, что буквально значит, что $x \in \bigcup_{n = 1}^{\infin} \bigcap_{k = n}^{\infin} A_k$

Получили, что $\lim\inf A_n \subseteq \bigcup_{n = 1}^{\infin} \bigcap_{k = n}^{\infin} A_k$

чтд

### Задача 5

Я не знаю, как писать эти масти карт в техе, поэтому введу замену ахах:

- пики: $A$
- бубны $B$
- крести: $C$
- черви: $D$

Вспомним [опред. $\sigma$-алгебры](https://github.com/financier-py/study_materials/blob/main/%D1%82%D0%B5%D0%BE%D1%80%D0%B2%D0%B5%D1%80_%D0%BC%D0%B0%D1%82%D1%81%D1%82%D0%B0%D1%82/%D1%82%D0%B5%D0%BE%D1%80%D0%B2%D0%B5%D1%80.pdf):

Множество $\mathcal{F}$, элементами которого являются подмножества множества $\Omega$ (не обязательно все), называется $\sigma$‑алгеброй, если выполнены следующие условия:

$(S1)$ $\Omega \in \mathcal{F}$

$(S2)$ если $A \in \mathcal{F}$, то $\overline{A} \in \mathcal{F}$ 

$(S3)$ если $A_1, A_2, \dotsc \in \mathcal{F}$, то $A_1 \cup A_2 \cup \dotsc \in \mathcal{F}$

#### пункт a

$$
S_1 = \set{\set{D, B, A}, \set{C}}
$$

Проверим условия из опреда. 

- $\Omega \in \sigma(S_1)$

- $\overline{\set{D, B, A}} = \set{C} \Rightarrow \set{C} \in \sigma(S_1)$, $\ \overline{\set{C}} = \set{D, B, A} \Rightarrow \set{D, B, A} \in \sigma(S_1)$, $\ \overline{\Omega} = \emptyset \Rightarrow \emptyset \in \sigma(S_1)$
 
- $\set{D, B, A} \cup {C} = \Omega$

Получается, что $\sigma(S_1) = \set{\Omega, \empty, \set{D, B, A}, \set{C}}$

#### пункт b

$$
S_2 = \set{\set{C}}
$$

Проверим условия из опреда. 

- $\Omega \in \sigma(S_2)$
  
- $\overline{\Omega} = \emptyset \Rightarrow \emptyset \in \sigma(S_2)$, $\ \overline{\set{C}} = \set{D, B, A} \Rightarrow \set{D, B, A} \in \sigma(S_2)$

Ну тут теперь стало все аналогично как в пункте а, поэтому 

$\sigma(S_2) = \set{\Omega, \empty, \set{D, B, A}, \set{C}}$

#### пункт с

$$
S_3 = \set{\set{A, D}, \set{B, C}}
$$

Проверим условия из опреда. 

- $\Omega \in \sigma(S_3)$
  
- $\overline{\Omega} = \emptyset \Rightarrow \emptyset \in \sigma(S_3)$, $\ \overline{\set{A, D}} = \set{B, C} \Rightarrow \set{B, C} \in \sigma(S_3)$, $\ \overline{\set{B, C}} = \set{A, D} \Rightarrow \set{A, D} \in \sigma(S_3)$
- $\set{A, D} \cup \set{B, C} = \Omega$

_(с пустым мн-вом не проверяю, потому что ну очев)_

Получаем, $\sigma(S_3) = \set{\Omega, \empty, \set{A, D}, \set{B, C}}$

#### пункт d

$$
S_4 = \set{\set{A, D}}
$$

Проверим условия из опреда. 

- $\Omega \in \sigma(S_4)$
  
- $\overline{\Omega} = \emptyset \Rightarrow \emptyset \in \sigma(S_4)$, $\ \overline{\set{A, D}} = \set{B, C} \Rightarrow \set{B, C} \in \sigma(S_4)$

Ну тут теперь дальше точно также как и в прошлом пункте, поэтому

Получаем, $\sigma(S_4) = \set{\Omega, \empty, \set{A, D}, \set{B, C}}$

#### пункт e

$$
S_5 = \set{\set{A, D}, \set{B}, \set{C}}
$$

Проверим условия из опреда. 

- $\Omega \in \sigma(S_5)$
  
- $\overline{\Omega} = \emptyset \Rightarrow \emptyset \in \sigma(S_5)$, $\ \overline{\set{A, D}} = \set{B, C} \Rightarrow \set{B, C} \in \sigma(S_5)$, $\ \overline{\set{B, C}} = \set{A, D} \Rightarrow \set{A, D} \in \sigma(S_5)$, $\ \overline{\set{B}} = \set{A, C, D} \Rightarrow \set{A, C, D} \in \sigma(S_5)$, $\ \overline{\set{C}} = \set{A, B, D} \Rightarrow \set{A, B, D} \in \sigma(S_5)$, $\ \overline{\set{A, C, D}} = \set{B} \Rightarrow \set{B} \in \sigma(S_5)$, $\ \overline{\set{A, B, D}} = \set{C} \Rightarrow \set{C} \in \sigma(S_5)$

- Тут достаточно рассмотреть объединения только тех множеств, чье объединение дает мн-во по мощности меньшее 4, ну иначе мы просто получим $\Omega$: $\ \set{A, D} \cup \set{B} = \set{A, B, D} \Rightarrow \set{A, B, D} \in \sigma(S_5)$ и $\set{A, D} \cup \set{C} = \set{A, C, D} \Rightarrow \set{A, C, D} \in \sigma(S_5)$

Получаем, $\sigma(S_5) = \set{\Omega, \empty, \set{A, D}, \set{B}, \set{C}, \set{A, B, D}, \set{A, C, D}}$

#### пункт f

$$
S_6 = \set{\set{A, D}, \set{C}}
$$

Проверим условия из опреда. 

- $\Omega \in \sigma(S_5)$
  
- $\overline{\Omega} = \emptyset \Rightarrow \emptyset \in \sigma(S_5)$, $\ \overline{\set{A, D}} = \set{B, C} \Rightarrow \set{B, C} \in \sigma(S_6)$, $\ \overline{\set{B, C}} = \set{A, D} \Rightarrow \set{A, D} \in \sigma(S_6)$, $\ \overline{\set{C}} = \set{A, B, D} \Rightarrow \set{A, B, D} \in \sigma(S_6)$, $\ \overline{\set{A, B, D}} = \set{C} \Rightarrow \set{C} \in \sigma(S_6)$
  
- $\set{A, D} \cup \set{C} = \set{A, C, D} \Rightarrow \set{A, C, D} \in \sigma(S_6)$. Все остальные объединения ничего нового не дадут, но тут мы получили одно новое мн-во. Тогда $\overline{\set{A, C, D}} = \set{B} \Rightarrow \set{B} \in \sigma(S_6)$. Ну а дополнение $\set{B}$ нам даст $\set{A, C, D}$, что уже есть 

Получаем, $\sigma(S_6) = \set{\Omega, \empty, \set{A, D}, \set{B}, \set{C}, \set{A, B, D}, \set{A, C, D}}$

Ответ: ответы даны выше после каждого пункта