# Прогнозирование заказов такси
[IPYNB](https://github.com/lil-scripter/practicum_projects/blob/980f1d7bcc416403c653ccfb8f2aeb47b3cd32ce/11-ML-cars_cost_prediction/11-ML-cars_cost_prediction.ipynb)

## Описание проекта

Сервис по продаже автомобилей с пробегом разрабатывает приложение для привлечения новых клиентов. В нём можно быстро узнать рыночную стоимость своего автомобиля.

В распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей. Нужно построить модель для определения стоимости. 

Заказчику важны:

- качество предсказания (RMSE < 2500);
- скорость предсказания;
- время обучения.


## Стек
pandas, sklearn, numpy, matplotlib, seaborn, phik, Ridge, DecisionTreeRegressor, RandomForestRegressor, lightgbm

## Общий вывод

Обучено 4 модели: линейная Ridge, дерево решений, случайный лес, градиентный бустинг LightGBM и случайная (для оценки результатов сложных моделей). Модели обучались с подбором гиперпараметров. Среди обученных моделей градиентный бустинг выдал лучшую метрику, однако обучение этой модели происходит медленнее других моделей. В то же время модель рандомного леса демонстрирует метрику, близкую к бустингу, но обучение проходит в два раза быстрее.

Важными критериями отбора моделей МО являются: качество и скорость предсказания, скорость обучения модели. Таким образом, с поставленной задачей предсказания цены автомобилей лучше стравится модель рандомного леса.

На тестовых данных учшая модель показала результат RMSE=1371, что удовлетворяет требованию к качеству модели.
