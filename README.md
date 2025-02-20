# Online-shop-research

## Описание проекта
Вы работаете в интернет-магазине «Стримчик», который продаёт по всему миру компьютерные игры. Из открытых источников доступны исторические данные о продажах игр, оценки пользователей и экспертов, жанры и платформы (например, Xbox или PlayStation). Вам нужно выявить определяющие успешность игры закономерности. Это позволит сделать ставку на потенциально популярный продукт и спланировать рекламные кампании.

## Описание данных
Перед вами данные до 2016 года. Представим, что сейчас декабрь 2016 г., и вы планируете кампанию на 2017-й. Нужно отработать принцип работы с данными. Неважно, прогнозируете ли вы продажи на 2017 год по данным 2016-го или же 2027-й — по данным 2026 года.

В наборе данных попадается аббревиатура ESRB (Entertainment Software Rating Board) — это ассоциация, определяющая возрастной рейтинг компьютерных игр. ESRB оценивает игровой контент и присваивает ему подходящую возрастную категорию, например, «Для взрослых», «Для детей младшего возраста» или «Для подростков».

Имеется файл с данными `games_csv` со следующей информацией:
<br>
`Name` — название игры
<br>
`Platform` — платформа
<br>
`Year_of_Release` — год выпуска
<br>
`Genre` — жанр игры
<br>
`NA_sales` — продажи в Северной Америке (миллионы проданных копий)
<br>
`EU_sales` — продажи в Европе (миллионы проданных копий)
<br>
`JP_sales` — продажи в Японии (миллионы проданных копий)
<br>
`Other_sales` — продажи в других странах (миллионы проданных копий)
<br>
`Critic_Score` — оценка критиков (максимум 100)
<br>
`User_Score` — оценка пользователей (максимум 10)
<br>
`Rating` — рейтинг от организации ESRB (англ. Entertainment Software Rating Board). Эта ассоциация определяет рейтинг компьютерных игр и присваивает им подходящую возрастную категорию.

## План проекта:
1. Изучим данные
2. Подготовим информацию к анализу
3. Проведем исследовательский анализ
4. Составим портрет пользователя каждого региона
5. Проверим некоторые гипотезы
6. Сделаем выводы

## В ходе работы над данным проектом было выполнено следующее:

1. Изучена общая информация о данных:
- датафрейм содержит 16715 строк, 11 столбцов
- в ряде колонок замечены пропуски
- в некоторых столбцах данные имеют неккоректный тип
- названия столбцов оформлены не в соответствии с корректным стилем оформления
2. Выполнена предобработка данных:
- изменены названия некоторых столбцов в соответствии со стандартами оформления
- выявлено отсутсвие явных дубликатов
- избавились от пропусков в некоторых столбцах путем удаления строк, содержащих их, в остальных столбцах принято решение их не трогать, дабы не повлиять на корректность данных
- изменены типы данных в столбцах `year_of_release`, `critic_score` и `user_score`
- добавлен столбец, содержащий информацию о суммарных продажах по всем регионам
3. Проведен исследовательский анализ данных:
- было проанализировано распределение игр по годам выпуска, принято решение рассматривать период последних трёх лет из-за стремительной динамики на рынке. Новые игры оказывают значительное воздействие на его развитие и тенденции.
- за весь период наблюдений наиболее высокие продажи наблюдались у платформ PS2, X360, PS3, Wii, DS и PS, что свидетельствует об их популярности среди пользователей.
- установлено, что средний срок жизни платформы составляет примерно 10 лет, что важно учитывать при прогнозировании тенденций на рынке.
- для актуального анализа был выбран период с 2014 по 2016 год. Это связано с высокой динамикой рынка, где новые игры появляются и исчезают очень быстро.
- по итогам последних лет PS4 и XOne стали самыми популярными платформами, показывая значительный отрыв в продажах, несмотря на наблюдаемый спад в 2016 году.
- анализ графиков, основанных на методе "ящик с усами", демонстрирует наибольший размах продаж у платформ PS4 и XOne, что ещё раз подтверждает их лидерство на рынке.
- связь между пользовательскими оценками и количеством продаж слабо выражена, что может указывать на её нелинейный характер.
- оценка критика довольно сильно влияет на продажи внутри платформы. Прослеживается линейная связь.
- среди наиболее популярных жанров выделяются экшн, ролевые игры и приключения
- самыми доходными жанрами признаны экшн и шутеры. Однако стоит отметить, что наибольший межквартильный размах наблюдается именно у жанров спорт и шутер, что делает их более перспективными и стабильными с точки зрения прибыли.
4. Cоставлен портрет пользователя каждого региона:
- Портрет пользователя региона Северной Америки практически совпадает с портретом пользователя Европы: популярные платформы `PS4`, `XOne`, жанр - `Action`, `Shooter`, категория `M`.
- Портрет пользователя Японии: платформа `3DS`, жанры `Role-Playing`, `Action`, категория `T`.
5. Проверены гипотезы:
- Существует вероятность утверждать, что средние пользовательские рейтинги платформ XOne и PC являются идентичными, поскольку при проведении т-теста не удалось опровергнуть нулевую гипотезу об их равенстве.
- Существует высокая вероятность, что средние пользователские рейтинги жанров Action и Sports отличаются друг от друга. Нулевая гипотеза об их равенстве была опровергнута.

### Подытожив всю информацию, сделаем финальный вывод.
Потенциально успешный продукт может иметь следующие параметры:
- рейтинг ESRB `M` (взрослые)
- платформа `PS4`, `XOne`
- жанр `Sports`, `Shooter` 
Cледует принять во внимание данные факторы при планировании рекламных кампаний.
