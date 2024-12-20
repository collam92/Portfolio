1. Запрос к Кликхаусу - комбинации календарных дат, URL и ID посетителей.sql
   
Этот запрос анализирует просмотры страниц на основе данных о поситителях (провайдерах) и URL-паттернах в заданном периоде времени,
для того, чтобы можно было отследить факт посещения/непосещения конкретных посетителей определенных URL страниц в опеределенные даты.
    Он включает следующие шаги:
   1) Фильтрация по времени: Запрос ограничивает данные определенным периодом времени (в примере с 1 августа 2024 года по 1 сентября 2024 года).
    2) Фильтрация по поситителям и URL-паттернам:
Используется массив идентификаторов провайдеров, которые были активны в этот период.
Применяется фильтрация URL по заранее заданным паттернам, что позволяет фокусироваться на определенных продуктах и страницах.
    Агрегация данных:
Для каждого провайдера и совпавшего паттерна URL определяется дата последнего посещения страницы и имя пользователя, который посетил страницу последним.
Если страница посещалась несколько раз за период - отображается имя последнего посетителя и дата последнего посещения
Исключаются запросы с определенными IP-адресами и суперпользователи.
    Создание временной таблицы для всех дат в указанном периоде:
Генерируется полный набор дат для заданного периода с привязкой к каждому провайдеру и паттерну URL.
    Основной запрос:
Для каждого дня в периоде, для каждого провайдера и URL проверяется, был ли просмотрен данный URL в этот день.
Для записей, где данные о просмотре есть, указывается дата последнего посещения и имя последнего пользователя.
Также добавляются данные о провайдере (название, город и менеджер по аккаунту).
Для каждого провайдера осуществляется обогащение данных из из справочников (например, название провайдера, город нахождения и тд).

2. Запрос к Кликхаусу - время проведённое отдельными пользователями и провайдерами на отдельных страницах продукта.sql.
   
Возвращает аггрегированое среднее и медианное время, проведённое пользователями и провайдерами на отдельных страницах продукта в определённый период времени.

3. Тестовое задание по Python (Титаник).
   
Результат выполнения одного из тестовых заданий - исследование известного датасета Титаник. 

4. Свод, Сравнение, Инструкция.
   
Программа, обьединяющая таблицы с разной структурой из нескольких источников в одну (4.1. Свод), и сравнивающая две таких таблицы за разный период и возвращающая список изменений (4.2. Сравнение), а также техническая инструкция по использованию данной программы для коллег, не знающих Python (4. Инструкция по работе).
