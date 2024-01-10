# MM-DSS

## Задание 6 - Модель Хольта-Уинтерса

**Цель работы:** получение прогноза для временного ряда с использование модели Хольта-Уинтерса.

Прогноз, получаемый с использованием модели Хольта-Уинтерса:
$x_{t+tau} = [tau*a(t) + b(t)] F(t+tau-L)$, где 

a(t) - линейно трендовая компонента;

b(t) - постоянная компонента;

F(t+tau-L) - сезонная компонента;

L - длина сезона.

Начальные параметры модели рассчитываются следующим образом:

$a(0), b(0)$ - коэффициенты парной линейной регрессии:

$x_t' = a(0)t + b(0)$

$F(-p) = 1/k * sum_{i=1}^k x_{x(p,i)} / x_{z(p,i)}'$, где

$k = n/L, p=1,...,L-1$

$z(p,i) = iL-p$.

Последующие параметры модели находятся итерационно по соответствующим формулам с использованием параметров сглаживания al_1, al_2, al_3:

$b(t) = al_1 y(t) / F(t-L) + (1-al_1) (b(t-1) + a(t-1))$

$a(t) = al_2 (b(t) - b(t-1)) + (1-al_2) a(t-1)$

$F(t) = al_3 y(t) / b(t) + (1-al_3) F(t-L)$

### Результаты моделирования

Прогнозные и фактические значения для тренировочной выборки
![image](https://github.com/cutttle/MM-DSS/assets/107594338/fd2dbd9c-993a-4627-88d9-dfdfa3dbb763)

Прогнозные и фактические значения для тестовой выборки
![image](https://github.com/cutttle/MM-DSS/assets/107594338/02d273ea-2b04-4644-9f4f-614c77532391)
