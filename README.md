
# Скрипты для изменения электронного дневника

Скрипт позволяет изменять оценки, удалять все записи с замечаниями, добавлять похвалы от учителя к ученику.

## Запуск

Для запуска необходимо установить [репозиторий с электронным дневником](https://github.com/devmanorg/e-diary/tree/master). 
Перенесите файлы `Похвалы.txt` и `scripts.py` в папку с проектом электронного дневника.
Откройте консоль на сервере и введите 
```
python manage.py shell
```

## Обзор возможностей

### Исправление всех плохих оценок
Исправляет "двойки" и "тройки" на "четверки, пятерки"(выбор исправленных оценок происходит случайным образом) 

Для того чтобы запустить данную возможность, введите в shell команду:
```python
from scripts import fix_marks
```
Далее введите, предварительно заменив данные в кавычках:
```python
fix_marks("ФИО", "Год_обучения", "Литера_класса")
```

`ФИО` - вводить полностью необязательно! Если у вас имя, фамилия или отчество уникальные в классе, то достаточно указать что-то одно из них. Для более точного поиска введите полностью ФИО.

`Год_обучения` - число, например `9`.

`Литера_класса` - литера класса, например `А`

### Удаление всех записей с замечаниями

Для того чтобы запустить данную возможность, введите в shell команду:
```python
from scripts import remove_chastisements
```
Далее введите, предварительно заменив данные в кавычках:
```python
remove_chastisements("Фамилия Имя Отчество", "Год_обучения", "Буква_класса")
```

Аналогично, что и с `исправлением плохих оценок`.

### Добавление записи с похвалой

Добавляет одну запись с похвалой для выбранного предмета. Урок и слова похвалы выбираются случайным образом. Для разнообразия, можно открыть файл `Похвалы.txt` и вставить новые фразы. Каждую фразу нужно вставлять на новой строчке!

Для того чтобы запустить данную возможность, введите в shell команду:
```python
from scripts import create_commendation
```
Далее введите, предварительно заменив данные в кавычках:
```python
create_commendation("Фамилия Имя Отчество", "Год_обучения", "Буква_класса", "Название_урока")
```

Аналогично, что и с `исправлением плохих оценок`, только нужно добавить `название_урока` - вводить строго как записано в электронном дневнике.