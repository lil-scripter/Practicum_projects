# Прогнозирование заказов такси
[IPYNB](https://github.com/lil-scripter/practicum_projects/blob/cb66928d32e84282ed943a4b35458000bb94ef7d/12-TSA-taxi_orders_prediction/12-TSA-taxi_orders_prediction.ipynb)

## Описание проекта

Компания такси собрала исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час.

**Цель**
Построить модель для предсказания количества заказов такси в следующий час.

**Задача**
Значение метрики RMSE на тестовой выборке должно быть не больше 48.

## Стек
pandas, sklearn, numpy, matplotlib, seaborn, shap, tsaplots, seasonal_decompose, RandomForestRegressor, Lasso

## Общий вывод

Во время EDA выявил:
* тенденцию увеличения количества заказов, причем, тренд растет нелинейно;
* суточную сезонность и недельную сезонность данных.
    
    
Добавлены новые признаки:
* ежечасные лаги в первые сутки;
* ежесуточные лаги до первой недели;
* еженедельные лаги до 4-ой недели;
* скользящее среднее значение за предыдущие 12, 24, 168 часов.


Было обучено 3 модели МО с подбором гиперпараметров и входных признаков. Наилучшей моделью оказалась модель с l1-регуляризацией и 11 входными признаками.


Лучшая модель показала на тестовых данных метрику RMSE равную 35, что удовлетворяет требованию к качеству модели.
