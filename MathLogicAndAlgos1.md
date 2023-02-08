# Математическая логика и теория алгоритмов

## Математическая логика

-- раздел математики, изучающий суждения.

### Аксиомы

-- первичные суждения, не требующие доказательства.

Аксиомы => Теоремы.

* Аксиомы связи
* Аксиомы порядка
* Аксиомы конгруентности

*Д. Гильберт.*

1. Связи
2. порядка
3. Аксиомы непрерывности
   * Акс. Архимеда ${\forall {a>0} \space \exist{n \in \natnums}:  n \cdot a>b }$
   * Акс. Полноты
4. Через ${M \in l}$ проходит не более одной прямой, не пересекающей данную прямую.

${A_1,...,A_{14} \not \implies A_{15}}$. ${A_{15}}$ - Аксиома, пятый постулат Евклида.

${A_1,...,A_{14}, \neg A_{15}}$ - геометрия Лобачевского

${A_1,...,A_{14}, A_{15}}$ - геометрия Евклидова

## Теория алгоритмов

### Исчисление высказываний (ИВ)

Язык ИВ:

1. пропозициональные переменные (атомарные формулы)  ${P_1, P_2,P_3, \dots}$
2. ${\neg,\vee, \wedge, \rightarrow}$ - логические связки
3. Вспомогательные символы
4. Знак вводимости

Формулы ИВ

Определение формулы строится индуктивно

1. пропозиционные переменные -- формулы
2. если $\alpha$ и $\beta$ - формулы, то и  ${\neg{\alpha}, ({\alpha}\vee{\beta}), ({\alpha}\wedge{\beta}), ({\alpha}\rightarrow{\beta})}$ - формулы

Синтаксис - формальная теория

Семантика - придание смысла

### Лемма

Пусть $\alpha$ и $\psi$ - формулы и $\phi$ - начало $\psi$, то ${\phi = \psi}$.

Доказательство:

Индукция по длина формулы $\phi$:

1. $|\phi|=1$, $\phi$ - атомарная $\implies$ $\psi$ - атомарная
2. Варианты:
     * $\phi$ начинается с "$\neg$" $\implies$ $\phi = \neg \phi_1$, где $\phi_1$ -формула, $\psi = \neg \psi_1 \implies \phi_1$ - начало $\psi_1$ $\implies$ $\phi_1  = \psi_1 \implies \phi  = \psi$.
     * $\phi$ начинается с "("

### Теорема

Любая неатомарная формула $\phi$ ИВ единственным образом представима ввиде $\phi = \neg \phi_1$, где $\phi_1$ - формула или $\phi = (\phi_1 \space \tau \space  \phi_2)$, ${\phi_1, \phi_2}$ - формулы, $\tau \in \{ \vee, \wedge,\rightarrow \}$.

Доказательство.

## Секвенция

$\phi_1,\phi_2,...,\phi_n \vdash \phi$,

$\phi_1,\phi_2,...,\phi_n,\phi$ - формулы

Доказываем секвенцией по правилам вывода!

## Правила вывода

| правила вставки (I) | правила удаления (E) |
| -----------------|------------------|
|${I_{\wedge}}$|${E_{\wedge}}$|
|$I_{\vee}$|${E_{\vee}}$|
|$I_{\neg}$|$E_{\neg}$|
|$I_{\rightarrow}$|$E_{\rightarrow}$|
||$E_{\perp}$|
---

### $I_{\wedge}$

$$
{\frac{\Gamma_1 \vdash \alpha \quad \Gamma_2 \vdash \beta}{\Gamma_1 , \Gamma_2 \vdash \alpha \wedge\beta } }
$$

### $I_{\vee}$

$$
{\frac{\Gamma \vdash \alpha }{\Gamma \vdash \alpha \vee\beta },\frac{\Gamma \vdash \beta }{\Gamma \vdash \alpha \vee\beta } }
$$

### $I_{\rightarrow}$

$$
{ \frac{\Gamma, \alpha \vdash \beta }{\Gamma \vdash \alpha \rightarrow\beta } }
$$

### $I_{\neg}$

$$
{\frac{\Gamma , \alpha \vdash}{\Gamma \vdash \neg \alpha }}
$$
----

### $E_{\wedge}$

$$
{\frac{\Gamma \vdash \alpha \wedge \beta }{\Gamma\vdash \alpha},\frac{\Gamma \vdash \alpha \wedge \beta }{\Gamma\vdash \beta}}
$$

### $E_{\vee}$

$$
{\frac{{\Gamma_1,\alpha \vdash \gamma } \quad {\Gamma_2,\beta \vdash \gamma } \quad{\Gamma_3 \vdash \alpha \vee \beta } }
{\Gamma_1,\Gamma_2,\Gamma_3 \vdash \gamma}}
$$

### $E_{\neg}$

$$
\frac
{{\Gamma_1 \vdash \alpha} \quad {\Gamma_2 \vdash  \neg\alpha}}
{\Gamma_1, \Gamma_2 \vdash}
$$

### $E_{\rightarrow}$

$$
\frac
{{\Gamma_1 \vdash \alpha} \quad {\Gamma_2 \vdash  \alpha \rightarrow \beta}}
{\Gamma_1, \Gamma_2 \vdash \beta}
$$

### $E_{\perp}$

$$
\frac
{\Gamma \vdash}
{\Gamma \vdash \alpha}
$$
---

### RAA - Reductio ad absurdum

$$
\frac
{\Gamma,\neg\alpha\vdash}
{\Gamma \vdash \alpha}
$$

Аксиомы - ${\Gamma, \alpha \vdash \alpha}$

Доказательства - набор формул ${S_1,S_2,\dots,S_n}$ такой, что ${\forall S_i }$ получается из предыдущего по правилам вывода, либо является аксиомой.

Примеры:

1. ${\alpha \wedge \beta \vdash \beta \wedge \alpha }$

$$
\frac{
   E_{\wedge}
     \frac{
        \alpha \wedge \beta \vdash \alpha \wedge \beta
        }
        {
        \alpha \wedge \beta \vdash \beta
        }
     \space
     \frac{\alpha \wedge \beta \vdash \alpha \wedge \beta}
     { \alpha \wedge \beta \vdash \alpha}
     E_{\wedge}
     }
     {
        \alpha \wedge \beta \vdash \beta \wedge \alpha
     }
      I_{\wedge}
$$

2.
