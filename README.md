Лабораторная работа №8.3. f Строки.  

# Практическое задание
## Задача 1.

Замените объединение строк на f-строку.  
```
def show_meteo(temperature, weather):
    print('Сейчас ' + weather + ', на градуснике ' + str(temperature) + '.')

show_meteo(24, 'облачно')
```

## Задача 2.

Замените в коде все объединения строк на f-строки.  

```
for messages_count in range(0, 21):
    if messages_count == 0:
        print('У вас нет новых сообщений')
    elif messages_count == 1:
        print('У вас 1 новое сообщение')
    elif messages_count <= 4:
        print('У вас ' + str(messages_count) + ' новых сообщения')
    else:
        print('У вас ' + str(messages_count) + ' новых сообщений')
```
# Выражения в f строках  

В f-строки можно подставлять не только переменные, но и результаты вычислений. Например, прямо в f-строке можно выполнять арифметические операции:  

```
# Сложение чисел
one_hundred = 100
five_hundred = 500
print(f'{one_hundred} + {five_hundred} = {one_hundred + five_hundred}')

# Сложение строк
one_hundred = 'сто'
five_hundred = 'пятьсот'
print(f'{one_hundred} + {five_hundred} = {one_hundred + five_hundred}')
# Будет напечатано: 
# 100 + 500 = 600
# сто + пятьсот = стопятьсот
```
В f-строке можно обратиться к элементам списка по индексу:  

```
russian_alphabet = ['а','б','в','г','д','е','ё','ж','з','и','й','к','л','м','н','о','п','р','с','т','у','ф','х','ц','ч','ш','щ','ъ','ы','ь','э','ю','я']

print(f'«{russian_alphabet[-1]}» - последняя буква в алфавите.')

# Будет напечатано: 
# «я» - последняя буква в алфавите.
```
Можно получить элемент словаря по ключу:  

```
favorite_songs = {
    'Тополиный пух': 'Иванушки international',
    'Город золотой': 'Аквариум',
    'Звезда по имени Солнце': 'Кино'
}

song = 'Город золотой'

print(f'«{song}» - одна из самых известных пеcен группы «{favorite_songs[song]}».')

# Будет напечатано: 
# «Город золотой» - одна из самых известных пеcен группы «Аквариум».
```
```
Хотя Python и позволяет вставлять сложные выражения внутрь f-строк, не злоупотребляйте этой возможностью. Иначе получится длинная перегруженная строка, в которой будет сложно разобраться.
```
Вот два примера одного и того же кода:  
```
favorite_songs = {
    'Тополиный пух': 'Иванушки international',
    'Город золотой': 'Аквариум',
    'Звезда по имени Солнце': 'Кино'
}

print(f'Из групп {favorite_songs["Тополиный пух"]}, {favorite_songs["Город золотой"]} и {favorite_songs["Звезда по имени Солнце"]} самая молодая — {favorite_songs["Тополиный пух"]}')
```
```
# А можно сделать код более аккуратным и читаемым
band_1 = favorite_songs['Тополиный пух']
band_2 = favorite_songs['Город золотой']
band_3 = favorite_songs['Звезда по имени Солнце']
print(f'Из групп {band_1}, {band_2} и {band_3} самая молодая команда — {band_1}')
```
Второй вариант намного понятнее, хотя строк стало больше.  
```
Лучше придерживаться общего правила: f-строки используются только для форматирования вывода, а все вычисления лучше проводить вне строк.
``` 
Не стоит экономить на количестве строчек, принося в жертву читаемость кода: как ни странно это звучит, код чаще читают, чем пишут!  

## Задача 3.

Научите Анфису сообщать время в формате ЧЧ:ММ:СС (часы, минуты, секунды). Программа должна напечатать На часах 19:28:06.  

```
def print_time(hour, minute, second):
    print(...)  # Аргумент должен содержать f-строку

print_time('19', '28', '06')
```
## Задача 4.

Функция `calc_stat()` принимает на вход список, в котором указана продолжительность прослушанных песен, в секундах.
Допишите код так, чтобы функция `calc_stat()` возвращала строку *`'Вы прослушали N песен.'`*, где **N** — длина списка, который был передан в функцию. **В решении примените f-строки.**
```
def calc_stat(listened):  # От англ. calculate statistics, посчитать статистику
    # Напишите код функции calc_stat()

print(calc_stat([189, 148, 210, 144, 174, 158, 163, 189, 227, 198]))
```

## Задача 5.

Допишите функцию `calc_stat():` выведите на экран суммарную статистику.  

+ ‘Вы прослушали **N** песен общей продолжительностью **M** минут.’
+ **N** — длина списка listened;
+ **M** — количество целых минут общей продолжительности прослушанных песен.
```
def calc_stat(listened):  # От англ. calculate statistics, посчитать статистику
    # Напишите код функции calc_stat()
        
    return f"Вы прослушали {len(listened)} песен."
print(calc_stat([189, 148, 210, 144, 174, 158, 163, 189, 227, 198]))
```

## Задача 6.

Вы знаете об f-строках достаточно, чтобы оптимизировать код Анфисы. Все фразы, которые сейчас составляет Анфиса, создаются через конкатенацию строк: фрагменты строк и значения переменных объединяются оператором +.  

Сделайте код проще: замените конкатенацию на f-строки. В коде отмечены места, где это нужно сделать.  

```
DATABASE = {
    'Серёга': 'Омск',
    'Соня': 'Москва',
    'Миша': 'Москва',
    'Дима': 'Челябинск',
    'Алина': 'Красноярск',
    'Егор': 'Пермь',
    'Коля': 'Красноярск'
}

def process_anfisa(query):
    if query == 'Сколько у меня друзей?':
        count = len(DATABASE)
        # В следующей строке замените конкатенацию на f-строку 
        return 'У тебя ' + str(count) + ' друзей.'
    elif query == 'Кто все мои друзья?':
        friends_string = ', '.join(DATABASE)
        # В следующей строке замените конкатенацию на f-строку 
        return 'Твои друзья: ' + friends_string
    elif query == 'Где все мои друзья?':
        unique_cities = set(DATABASE.values())
        cities_string = ', '.join(unique_cities)
        # В следующей строке замените конкатенацию на f-строку 
        return 'Твои друзья в городах: ' + cities_string
    else:
        return '<неизвестный запрос>'


print('Привет, я Анфиса!')
print(process_anfisa('Сколько у меня друзей?'))
print(process_anfisa('Кто все мои друзья?'))
print(process_anfisa('Где все мои друзья?'))
```

# Запросы к друзьям

Анфиса уже умеет отвечать на несколько общих вопросов:
Сколько у меня друзей?  

+ Кто все мои друзья?
+ Где все мои друзья?

Вам предстоит расширить возможности Анфисы: она научится отвечать на вопросы об отдельных друзьях.  

Отличать вопросы к Анфисе от вопросов про отдельных друзей программа будет по первому слову запроса, по имени. Для этого каждый запрос должен начинаться с обращения:  

+ Анфиса, сколько у меня друзей?
+ Дима, ты где?
+ Анфиса, кто все мои друзья?
+ Соня, ты где?

Получив вопрос `Дима, ты где?` Анфиса найдёт нужную информацию в словаре DATABASE и ответит `Дима в городе Челябинск`.  

Анфиса научится отличать, кому задан вопрос, выделив имя из строки с вопросом.  

Но для начала научим Анфису говорить грамотно.  

## Задача 7.

Это код Анфисы, который вы последовательно писали на протяжении нескольких тем. В него добавлена функция `format_friends_count()`, но она пока нигде не вызывается.

Перечитайте и запустите код: освежите в памяти, как обрабатываются запросы к Анфисе.  

А после этого — за работу!  

Научите Анфису говорить грамотно. В словаре `DATABASE` семь элементов, и на вопрос «Анфиса, сколько у меня друзей» программа отвечает: «У тебя 7 друзей».  

Но если в словаре будет лишь один друг — Анфиса напишет «у тебя 1 друзей», а грамотные программы так не говорят!  

Функцию со склонениями числительных вы уже написали, она добавлена в код. Осталось «прикрутить» её к Анфисе.  

Из функции `process_anfisa()`, из блока `if query == 'сколько у меня друзей?'` вызовите функцию `format_friends_count()` и вставьте возвращаемую этой функцией фразу в f-строку так, чтобы на вопрос `'сколько у меня друзей'` функция возвращала грамотный ответ, например, `У тебя 9 друзей или У тебя 3 друга.`.  

```
DATABASE = {
    'Серёга': 'Омск',
    'Соня': 'Москва',
    'Миша': 'Москва',
    'Дима': 'Челябинск',
    'Алина': 'Красноярск',
    'Егор': 'Пермь',
    'Коля': 'Красноярск'
}

# Новая функция, она возвращает правильное словосочетание, склоняя слово "друзья" 
# в зависимости от того, какое число передано в аргументе friends_count
def format_friends_count(friends_count):
    if friends_count == 1:
        return '1 друг'
    elif 2 <= friends_count <= 4:
        return f'{friends_count} друга'
    else:
        return f'{friends_count} друзей'


def process_anfisa(query):
    if query == 'сколько у меня друзей?':
        count = len(DATABASE)
        # Вызовите функцию format_friends_count() и передайте в неё count.
        # Отредактируйте строку ниже: в ней должно использоваться выражение, 
        # которое вернёт функция format_friends_count()
        return f'У тебя {count} друзей.'
    elif query == 'кто все мои друзья?':
        friends_string = ', '.join(DATABASE)
        return f'Твои друзья: {friends_string}'
    elif query == 'где все мои друзья?':
        unique_cities = set(DATABASE.values())
        cities_string = ', '.join(unique_cities)
        return f'Твои друзья в городах: {cities_string}'
    else:
        return '<неизвестный запрос>'


print('Привет, я Анфиса!')
print(process_anfisa('сколько у меня друзей?'))
print(process_anfisa('кто все мои друзья?'))
print(process_anfisa('где все мои друзья?'))
print(process_anfisa('кто виноват?'))
```

## Задача 8.

Сделаем так, чтобы можно было задавать вопросы не только Анфисе, но и самим друзьям, обращаясь к ним по имени. А друзья ответят, в каком они городе.  

Добавим в запросы имена. Вопрос к Анфисе будет звучать так: **`Анфиса, где все мои друзья?`**  
Ответ на этот вопрос уже подготовлен, надо лишь немного изменить код.  

А вопрос к кому-то из друзей будет таким: **`Коля, ты где?`**. Анфиса должна ответить: **`Коля в городе Красноярск`**.  

Структура кода:  

+ в первую очередь теперь будет вызываться функция `process_query(query)` (вы сейчас её напишете), она получает запрос и разделяет его на **имя** и **вопрос** (например, запрос `Анфиса, где все мои друзья?` должен быть разделён на `Анфиса` и `где все мои друзья?`);
+ если в запросе передано имя Анфиса — будет вызываться функция `process_anfisa()` с аргументом — вопросом (например — `где все мои друзья?`);

1. Объявите в коде функцию `process_query(query)`, в ней с помощью метода `split()` разделите строку `query` на две части: на имя и вопрос.
2. После этого напишите проверку, ветвление `if`:
    + если имя — «Анфиса», вызовите функцию `process_anfisa()`, при вызове передайте в неё аргументом вопрос, получившийся при разделении строки `query`. Верните результат выполнения этой функции.
    + если же имя — не «Анфиса», то функция не должна делать вообще ничего: этот вариант обработаем в следующей задаче.
  
3. Отредактируйте список вызовов функции, размещённый в конце программы:
    + должна вызываться функция `process_query()`, вызовы должны выглядеть так: `print(process_query('Текст_запроса'))`
    + все запросы должны начинаться с имени Анфиса:
         + Анфиса, сколько у меня друзей?
         + Анфиса, кто все мои друзья?
         + Анфиса, где все мои друзья?
         + Анфиса, кто виноват?
     
    + добавьте ещё один вызов, для проверки: `print(process_query('Соня, ты где?'))`. На этот запрос Анфиса вернет **None**, но не сломается.
      

## Задача 9.

Объявите функцию `process_friend(name, query)`, принимающую имя друга `name` и запрос `query`. В этой функции будут обрабатываться запросы, в которых имя — не «Анфиса».

В функции `process_friend()` напишите ветвление: если друг с именем name есть в словаре `DATABASE`: если переменная `query` содержит строку `'ты где?'` — функция должна вернуть сообщение `'{имя_друга} в городе {название_города}'`; название города нужно получить из словаря `DATABASE`.

+ если переменная query содержит какую-то другую строку — функция должна вернуть сообщение `<неизвестный запрос>`.
+ если друга с именем name нет в словаре `DATABASE` — функция должна вернуть сообщение: `У тебя нет друга по имени {имя_друга}`.

Теперь нужно дописать функцию `process_query()`.  

Добавьте в ветвление `if name == 'Анфиса'` блок `else:` если запрос начинается не с имени `«Анфиса»` — верните результат вызова функции `process_friend()`, передав в неё два аргумента: имя друга и текст вопроса.

Добавьте новые вызовы функции `process_query()`:  

```
print(process_query('Коля, что делать?'))
print(process_query('Антон, ты где?'))
```
      

       













