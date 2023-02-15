# Семантика

|Истина |ложь|
|-|-|
|1 | 0|

$$
F_{atom} \rightarrow \{ 0,1 \}
$$
$$
\theta - оценка
$$
Единственным образом продолжается до
$$
\theta : F \rightarrow \{ 0,1 \}
$$
и индуктивно
$$
\theta (\neg \alpha) = 1 - \theta(\alpha) = \neg \theta (\alpha)
$$

$$
\theta (\alpha \wedge \beta) = min( \theta(\alpha), \theta (\beta)) =  \theta (\alpha) \wedge \theta (\beta)
$$

$$
\theta (\alpha \vee \beta) = max( \theta(\alpha), \theta (\beta)) =  \theta (\alpha) \vee \theta (\beta)
$$

$$
\theta (\alpha \rightarrow \beta) =\neg  \theta (\alpha) \vee \theta (\beta)
$$

## Секвенции

$$
Seq \rightarrow \{ 0,1 \}
$$

Виды

1. $\phi_1,\phi_2,...,\phi_n \vdash \phi$
2. $\phi_1,\phi_2,...,\phi_n \vdash$
3. $\qquad\qquad\quad\space\space\vdash \phi$

Определение

 ${\theta( \phi_1,\phi_2,...,\phi_n \vdash \phi)=1 <=>}$ какой-либо из ${\theta( \phi_1),\theta(\phi_2),...,\theta(\phi_n) = 0}$ или  ${\theta(\phi) =1}$

## Теорема о полноте

Секвенция доказуема <=> она тождественна.
Формула доказуема <=> она тождественно истинна.

${\phi}$ - формула
${p_1,\dots,p_n}$ - пропозиционные входящие в $\phi$

${\phi}$ истинна на наборе 0,0,1,0,1

${\theta( \phi_1,\phi_2,...,\phi_n \vdash \phi)=0}$ - секвенция ложна на наборе ...

формула называется тождественно истинной, если она истинна на любом наборе.

${p \rightarrow p \vee q}$ тождественно истинна

${p \rightarrow (p \wedge q)}$ не является тождественно истинной

Утв.

${\Gamma, \alpha \vdash \beta}$ док ${\iff \Gamma \vdash \alpha \rightarrow \beta}$ доказуема

${\Gamma, \alpha \vdash \beta}$ тожд. ист. ${\iff \Gamma \vdash \alpha \rightarrow \beta}$ тожд. ист.

Пусть
${\Gamma, \alpha \vdash \beta}$ доказуема

$$
\frac
{\Gamma, \alpha \vdash \beta}
{ \Gamma \vdash \alpha \rightarrow \beta}
I_{\rightarrow}
$$

Докажем, что если ${\Gamma, \alpha \vdash \beta}$ ист на каком-либо наборе, то ${ \Gamma \vdash \alpha \rightarrow \beta}$ ист на том же наборе. И наоборот. (Наоборот)

$\theta ({\Gamma, \alpha \vdash \beta})=1$ это значит что либо

1. какая либо из $\Gamma$ ложна (+)
2. альфа ложна ${\implies \alpha \rightarrow \beta }$ истинна (+)
3. бета истинна ${\implies \alpha \rightarrow \beta }$ истинна (+)

Определение

Пусть $\Gamma$ - множество формул ИВ (не обязатльно конечное)

Гамма -  противоречивое множество формул, если существует конечное подмножество ${\Gamma_0} \subseteq \Gamma$, такое что ${\Gamma_0} \vdash$ -  доказуемо

Псевдосеквенции

* ${\Gamma \vdash}$
* ${\Gamma \vdash \phi}$
* ${\vdash \phi}$

$\Gamma$ противоречива, если ${\Gamma \vdash}$ "доказуема"

${\Gamma_0\vdash}$

Множество ${\Gamma}$ выполнимо если существует оценка ${\theta}$, что все формулы из ${\Gamma_0}$ будут истинны.

....

$$
\frac{\Gamma_1,\alpha \vdash \gamma \quad\Gamma_2,\beta \vdash \gamma\quad\Gamma_3 \vdash \alpha \vee \beta }{\Gamma_1,\Gamma_2,\Gamma_3 \vdash \gamma}
$$
Пусть на каком либо наборе числитель истинна

Надо доказать, что на этом же наборе знаменатель - истина

Пусть это не так, тогда

${\theta (\Gamma_1,\Gamma_3,\Gamma_3 \vdash \gamma)=0}$

Все из ${\Gamma_1, \Gamma_2,\Gamma_3}$ - истинны, а ${\gamma}$ - ложна

${\theta(\alpha)=0}$

${\theta(\beta)=0}$

${\Gamma_3 \vdash \alpha \vee \beta}$ - ложна, противоречие!

...

${\Gamma}$ не противоречива, если ${\Gamma \vdash}$ недоказуема

## Свойства не противоречивых множеств высказываний формул

Утв. Всякое непротиворечивое множество формул ${\Gamma}$ продолжается до максимального непротиворечивого множества формул ${\Gamma^*}$

Максимально по включению

${\Gamma \subseteq \Gamma^*}$

Доказательство

${p_1,p_2,p_3,\dots,}$ - счетное множество атомарных формул

Всех формул -  тоже счетное число.

* формулы длины 1 : ${p_1,p_2,p_3,\dots}$ - счетное число
* формулы длины 2 : ${\neg p_1,\neg p_2, \neg p_3,\dots}$ - счетное число
* формулы длины 3 : ${\neg\neg p_1,\neg\neg p_2, \neg\neg p_3,\dots}$ - счетное число
* формулы длины 4 : ${\neg\neg\neg p_1,\neg\neg\neg p_2, \neg\neg\neg p_3,\dots}$ - счетное число
* формулы длины 5 : ${\neg\neg\neg\neg p_1,\neg\neg\neg p_2, \dots, (p_1 \vee p_2), (p_1 \wedge p_2), (p_1 \rightarrow p_2)\dots}$ - счетное число
* ...

${F =  \{ \phi_1,\phi_2,\dots\}}$ -все формулы

$${\Gamma^{(0)}=\Gamma}$$

$$
\Gamma^{(n+1)} =
\begin{equation*}
   \begin{cases}
      \Gamma ...
      \\
      \Gamma ...
   \end{cases}
\end{equation*}
$$


## Свойства максимального непротиворечивого

1. для любой формулы ${\phi}$: ${\phi \in \Gamma^{*}}$ или ${\neg\phi \in \Gamma^{*}}$


...