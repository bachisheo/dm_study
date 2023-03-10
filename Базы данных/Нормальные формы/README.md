# Нормальные формы
### Функциональные зависимости 
Пусть X и Y — некоторые множества атрибутов одного отношения.   
Тогда Y функционально зависит от X (X → Y), если для любой комбинации значений атрибутов из X может существовать только одна комбинация значений
Y, входящая в отношение.

Тривиальная зависимость: если Y ⊂ X, то X → Y

## Ключи
* Возможный (superkey) ключ отношения: множество атрибутов, от которого функционально зависят все атрибуты отношения (уникальный в каждом отношении)
* Минимальный, потенциальный (candidate key) ключ отношения - возможный ключ, если после исключения из него любого атрибута оставшееся множество атрибутов не является возможным ключом. Все его атрибуты - prime
* Первичный (primary key) ключ отношения - один из минимальных ключей  
Он не имеет значения для реляционной теории, однако важен для её применения. Разные кортежи с одинаковыми значениями первичного ключа описывают разные состояния одного реального объекта.
* Внешний ключ - набор атрибутов, которые соответсвуют первичному ключу другого отношения 
## Нормализация 
Источник - https://habr.com/ru/post/254773/  

Нормальная форма — требование, предъявляемое к структуре таблиц в теории реляционных баз данных для устранения из базы избыточных функциональных зависимостей между атрибутами (полями таблиц).

Метод нормальных форм (НФ) состоит в сборе информации об объектах решения задачи в рамках одного отношения и последующей декомпозиции этого отношения на несколько взаимосвязанных отношений на основе процедур нормализации отношений.

Цель нормализации: исключить избыточное дублирование данных, которое является причиной аномалий, возникших при добавлении, редактировании и удалении кортежей.

Аномалия - такая ситуация в таблице БД, которая приводит к противоречию в БД либо существенно усложняет обработку БД. Причиной является излишнее дублирование данных в таблице, которое вызывается наличием функциональных зависимостей от не ключевых атрибутов.

Аномалии-модификации: изменение одних данных может повлечь просмотр всей таблицы и соответствующее изменение некоторых записей таблицы.

Аномалии-удаления — при удалении какого либо кортежа из таблицы может пропасть информация, которая не связана на прямую с удаляемой записью.

Аномалии-добавления: информацию в таблицу нельзя поместить, пока она не полная, либо вставка записи требует дополнительного просмотра таблицы.

* нельзя добавить группу, пока в ней нет студента

### 1НФ
* все атрибуты отношения являются простыми (атомарные, т.е. только 1 значение)
* все используемые домены должны содержать только скалярные значения. 
* Нет повторений строк в таблице.

### 2НФ
* 1 НФ
* каждый не ключевой атрибут неприводимо зависит от Потенциального

Неприводимость означает, что в составе потенциального ключа отсутствует меньшее подмножество атрибутов, от которого можно также вывести данную функциональную зависимость.

Делаем из плохой таблицы две ее проекции, при соединении они дают исходную

### 3НФ 
* 2НФ
* не ключевой атрибут нетранзитивно зависит от ПК, т.е. транзитивные связи от ПК нужно устранять



### BCNF - нормальная форма Бойса — Кодда
Все функциональыне зависимости
* Либо от возможного ключа
* Либо тривиальная зависимость (подмножества от надмножества)

### 4НФ 
* многозначные зависимости

### 5НФ 
* Максимально возможное разложение без потерь информации

Все нормальные формы хороши, только как "на поле" узнать, где именно есть функциональные зависимости, а где нет? А что если связь случайная?   
Эти формы применяютяс на практике, но не совмес корректно.

Функциональные зависимости можно извлечь из модели сущность-связь, а она сразу в 3НФ и других функциональных зависимостей мы из нее не получим.

Зная функциональные зависимости между отрибутами можно получить 3НФ с помощью изветсных алгоритмов за полиномиально время.


## Теоретическая РМ
* нет неопределенных значений (NULL). Ложь на логических операциях с NULL!
* нет дубликатов
* нет внещних соединений (результатом мб NULL), некоторые операции различны
* естественная идентификация по значениям атрибутов
* идентификация определяется функциональными зависимостями
* связи вычисляются при выполнении операции соединения 
* ассоциотивный доступ к данным по значениям (операция селекции)

Нереляционные модели данных либо не корректны, либо в основе своей содержат РМ, т.к. она проявляется во всех системах, в которых есть булева логика и формирование множества из другого множества.