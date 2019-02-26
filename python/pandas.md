#Библиотека Pandas

Pandas позволяет работать с данными в виде таблиц. Основные классы - 
 [
 DataFrame - это таблица или матрица, которая имеет строки и колонки. Строки автоматически индексируются числами от 0, колонки имеют названия (labels). Примеры создания DataFrame - 
 [
 pd.read_csv('name.csv', header='number of row with headers', sep='separator')
 pd.DataFrame([{'name': 'name', 'age': 10}, {'name': 'name', 'age': 10}])
 ]
 Series - это колонка в DataFarem или вектор
 ]

import pandas as pd
frame = pd.DataFrame()

Добавление строки
frame.append({new_line}, ignore_index=True)

Добавление столбца в DataFrame
frame['columnName'] = [...]

Удаление строк DataFrame (axis = 0 удаление строк, 1 удаление столбцов)
frame.drop([id или labels], axis=0)

Запись DataFrame в файл
frame.to_csv('name.csv', sep=',', header=True, index=False)

Показывает типы столбцов
frame.dtypes

Изменение типа столбца с помощью функции apply
frame.Coumnname = frame.Coumnname.apply(pd.to_datetime)

Показывает информацию по таблице
frame.info()

Заполнение пропущенных значений с помощью метода fillna
frame.fillna('UNKNOWN')

Срез по названиям колонок
frame[['Position',...]]

Срез по индексам строк
frame[:3] 

Срезы по колонкам и строкам
frame.loc[[0,1,2], ["Name", "City"]]  - используются названия колонок
frame.iloc[[1,3,5], [0,1]]  - используются ииндексы колонок
frame.ix[[0,1,2], ["Name", "City"]]  - индесы и названаия

Фильтрация
frame[frame.Columnname >= pd.datetime(1985,1,1)]
frame[(frame.Columnname1 >= pd.datetime(1985,1,1)) &
      (frame.Columnname2 != 'Москва')]