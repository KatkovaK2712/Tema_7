# ТЕМА 7. Работа с файлами (ввод, вывод)
Отчет по Теме #7 выполнил(а):
- Каткова Ксения Александровна
- ПИЭ-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + | - |
| Задание 7 | + | - |
| Задание 8 | + | - |
| Задание 9 | + | - |
| Задание 10 | + | - |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
Составьте текстовый файл и положите его в одну директорию с программой на Python. Текстовый файл должен состоять минимум из двух строк.

```python
Привет, мир!
Не хочу на тестирование 😢
```
### Результат.
![image](https://github.com/user-attachments/assets/eab795a9-a693-4de0-8371-f30b1d71a341)

## Выводы
Файл создан.

## Лабораторная работа №2
Напишите программу, которая выведет только первую строку из вашего файла, при этом используйте конструкцию open()/close().

```python
file = open('aaa.txt', 'r', encoding='utf-8')
first_line = file.readline().strip()
file.close()
print(first_line)
```
### Результат.
![image](https://github.com/user-attachments/assets/ef18ae59-39a1-4bbd-8d70-91a2ce3869b8)

## Выводы
Программа выводит первую строку файла: "Привет, мир!"

## Лабораторная работа №3
Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию open()/close(). 

```python
file = open('aaa.txt', 'r', encoding='utf-8')
lines = file.readlines()
file.close()
print([line.strip() for line in lines])
```
### Результат.
![image](https://github.com/user-attachments/assets/7d20c993-87c1-4706-bf5a-42c16708eb90)

## Выводы
Программа выводит массив со всеми строками.

## Лабораторная работа №4
Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию with open().

```python
with open('aaa.txt', 'r', encoding='utf-8') as file:
    lines = file.readlines()
print([line.strip() for line in lines])
```
### Результат.
![image](https://github.com/user-attachments/assets/dc04417b-a796-493a-bc13-f458d760c957)

## Выводы
Программа выводит массив со всеми строками.

## Лабораторная работа №5
Напишите программу, которая выведет каждую строку из вашего файла отдельно, при этом используйте конструкцию with open().

```python
with open('aaa.txt', 'r', encoding='utf-8') as file:
    for line in file:
        print(line.strip())
```
### Результат.
![image](https://github.com/user-attachments/assets/106280f9-4d2a-44d6-a7f7-0d83775cd442)

## Выводы
Каждая строка выводится по отдельности.

## Лабораторная работа №6
Напишите программу, которая будет добавлять новую строку в ваш файл, а потом выведет полученный файл в консоль. Вывод можно осуществлять любым способом. Обязательно проверьте сам файл, чтобы изменения в нем тоже отображались.

```python
with open('aaa.txt', 'a', encoding='utf-8') as file:
    file.write('\nЭто новая строка.')
with open('aaa.txt', 'r', encoding='utf-8') as file:
    print(file.read())
```
### Результат.
![image](https://github.com/user-attachments/assets/12ada5db-a37c-465e-b6b2-1e35a29fa7c4)

## Выводы
Файл теперь включает новую строку. Изменения сохранены и отображены.

## Лабораторная работа №7
Напишите программу, которая перепишет всю информацию, которая была у вас в файле до этого, например напишет любые данные из произвольно вами составленного списка. Также не забудьте проверить что измененная вами информация сохранилась в файле. 

```python
data = ['Первая строка', 'Вторая строка', 'Третья строка']
with open('aaa.txt', 'w', encoding='utf-8') as file:
    for line in data:
        file.write(line + '\n')
with open('aaa.txt', 'r', encoding='utf-8') as file:
    print(file.read())
```
### Результат.
![image](https://github.com/user-attachments/assets/72f757dd-956b-46a7-a6ae-a3df08298a36)

## Выводы
Файл теперь содержит новые строки из списка. Изменения сохранены.

## Лабораторная работа №8
Выберите любую папку на своем компьютере, имеющую вложенные директории. Выведите на печать в терминал ее содержимое, как и всех подкаталогов при помощи функции print_docs(directory).

```python
import os
def print_docs(directory):
    for root, dirs, files in os.walk(directory):
        for name in files:
            print(os.path.join(root, name))
print_docs(r'C:\Users\User\PycharmProjects\lab_2')
```
### Результат.
![image](https://github.com/user-attachments/assets/7fc64211-df86-44e8-a35e-80511574f23d)

## Выводы
Все файлы и папки выводятся в терминал.

## Лабораторная работа №9
Документ «input.txt» содержит следующий текст: 
Приветствие
Спасибо 
Извините 
Пожалуйста 
До свидания 
Ты готов?
Как дела?
С днем рождения! 
Удача!
Я тебя люблю.
Требуется реализовать функцию, которая выводит слово, имеющее максимальную длину (или список слов, если таковых несколько).
Проверьте работоспособность программы на своем наборе данных.

```python
def max_l(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        words = file.read().split()
    max_length = max(len(word) for word in words)
    return [word for word in words if len(word) == max_length]
print(max_l('aaa.txt'))
```
### Результат.
![image](https://github.com/user-attachments/assets/2a4b4b40-fdf1-4e30-9d99-fa18b382a572)

## Выводы
Программа выводит самое длинное слово или слова из файла.

## Лабораторная работа №10
Требуется создать csv-файл «rows_300.csv» со следующими столбцами:
•	№ - номер по порядку (от 1 до 300);
•	Секунда – текущая секунда на вашем ПК;
•	Микросекунда – текущая миллисекунда на часах.
Для наглядности на каждой итерации цикла искусственно приостанавливайте скрипт на 0,01 секунду.

```python
import csv
import time
with open('file_csv.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile)
    writer.writerow(['№', 'Секунда', 'Микросекунда'])
    for i in range(1, 301):
        seconds = time.localtime().tm_sec
        microseconds = int(time.time() * 1e6) % 1e6
        print(f"Строка {i}: Секунды - {seconds}, Микросекунды - {microseconds}")
        writer.writerow([i, seconds, microseconds])
        time.sleep(0.01)
```
### Результат.
![image](https://github.com/user-attachments/assets/80d39144-a7bd-4833-8121-451464508697)

## Выводы
CSV-файл rows_300.csv создан с указанными данными.

## Самостоятельная работа №1
Найдите в интернете любую статью (объем статьи не менее 200 слов), скопируйте ее содержимое в файл и напишите программу, которая считает количество слов в текстовом файле и определит самое часто встречающееся слово. Результатом выполнения задачи будет: скриншот файла со статьей, листинг кода, и вывод в консоль, в котором будет указана вся необходимая информация.

```python
from collections import Counter
with open('aaa.txt', 'r', encoding='utf-8') as file:
    text = file.read()
words = text.split()
word_count = len(words)
word_freq = Counter(words)
most_common_word, most_common_count = word_freq.most_common(1)[0]
print(f'Количество слов: {word_count}')
print(f'Самое частое слово: "{most_common_word}" (встречается {most_common_count} раз)')
```
### Результат.
![image](https://github.com/user-attachments/assets/52ed6f7f-a06e-4db8-9c5a-52cf5d9c8111)

Использованный текст:

![image](https://github.com/user-attachments/assets/75a47bb0-0c79-4053-a2f3-9d31f602729c)

## Выводы
Программа показывает общее количество слов и самое частое слово с его частотой.

## Самостоятельная работа №2
У вас появилась потребность в ведении книги расходов, посмотрев все существующие варианты вы пришли к выводу что вас ничего не устраивает и нужно все делать самому. Напишите программу для учета расходов. Программа должна позволять вводить информацию о расходах, сохранять ее в файл и выводить существующие данные в консоль. Ввод информации происходит через консоль. Результатом выполнения задачи будет: скриншот файла с учетом расходов, листинг кода, и вывод в консоль, с демонстрацией работоспособности программы.

```python
def add_expense():
    description = input("Введите описание расходов: ")
    amount = input("Введите сумму расходов: ")
    with open('aaa.txt', 'a', encoding='utf-8') as file:
        file.write(f'{description}: {amount}\n')
def show_expenses():
    print("Записи расходов:")
    with open('aaa.txt', 'r', encoding='utf-8') as file:
        for line in file:
            print(line.strip())
while True:
    action = input("Введите 'добавить' для добавления расхода или 'показать' для вывода всех расходов: ").strip()
    if action.lower() == 'добавить':
        add_expense()
    elif action.lower() == 'показать':
        show_expenses()
    else:
        print("Неверный ввод. Попробуйте снова.")
```
### Результат.
![image](https://github.com/user-attachments/assets/a2d4a055-7321-41ca-a541-e0747d2d8c75)

## Выводы
Программа позволяет добавлять и показывать записи расходов.

## Самостоятельная работа №3
Имеется файл input.txt с текстом на латинице. Напишите программу, которая выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.
•	Текст в файле: Beautiful is better than ugly. Explicit is better than implicit. Simple is better than complex.
Complex is better than complicated.
•	Ожидаемый результат: Input file contains:
108 letters
20 words
4 lines

```python
def text_statistics(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        text = file.read()
    letters_count = sum(c.isalpha() for c in text)
    words_count = len(text.split())
    lines_count = text.count('\n') + 1
    print(f"Input file contains:")
    print(f"{letters_count} letters")
    print(f"{words_count} words")
    print(f"{lines_count} lines")
text_statistics('aaa.txt')
```
### Результат.
![image](https://github.com/user-attachments/assets/a0deefea-5151-4e71-8289-0518212c943d)

## Выводы
Программа выводит количество букв, слов и строк из файла. 

## Самостоятельная работа №4
Напишите программу, которая получает на вход предложение, выводит его в терминал, заменяя все запрещенные слова звездочками * (количество звездочек равно количеству букв в слове). Запрещенные слова, разделенные символом пробела, хранятся в текстовом файле input.txt. Все слова в этом файле записаны в нижнем регистре. Программа должна заменить запрещенные слова, где бы они ни встречались, даже в середине другого слова. Замена производится независимо от регистра: если файл input.txt содержит запрещенное слово exam, то слова exam, Exam, ExaM, EXAM и exAm должны быть заменены на ****.
•	Запрещенные слова:
hello email python the exam wor is
•	Предложение для проверки:
Hello, world! Python IS the programming language of thE future. My EMAIL is ksusha.katkova2468@yandex.ru
PYTHON is awesome!!!!
•	Ожидаемый результат:
*****, ***ld! ****** ** *** programming language of *** future. My
***** ** ksusha.katkova2468@yandex.ru
****** ** awesome!!!!

```python
import re
def censor_text(input_text, banned_words):
    for word in banned_words:
        input_text = re.sub(word, '*' * len(word), input_text, flags=re.IGNORECASE)
    return input_text
with open('aaa.txt', 'r', encoding='utf-8') as file:
    banned_words = file.read().strip().split()
sentence = input("Введите предложение для проверки: ")
censored_sentence = censor_text(sentence, banned_words)
print(censored_sentence)

```
### Результат.
![image](https://github.com/user-attachments/assets/709998de-6c74-45e7-96b2-7305cda7a1d3)

## Выводы
Программа заменяет запрещенные слова в вводимом предложении на звездочки.

## Самостоятельная работа №5
Самостоятельно придумайте и решите задачу, которая будет взаимодействовать с текстовым файлом.
Подсчет строк в файле и вывод их на экран.

```python
def print_lines(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        for line_num, line in enumerate(file, 1):
            print(f"{line_num}: {line.strip()}")
print_lines('aaa.txt')
```
### Результат.
![image](https://github.com/user-attachments/assets/8018284b-1d06-4085-bff7-39c9bd6f6240)

## Выводы
Программа выводит строки файла с их номерами.

## Общие выводы по теме

1. Основные операции с файлами
Были изучены методы для работы с файлами. Основные операции включают:
- Чтение (read(), readline(), readlines()): позволяет загружать данные из файла в переменные для обработки.
- Запись (write(), writelines()): позволяет сохранять данные в файл.
- Открытие (open()): используется для открытие файла с заданными параметрами (режимы чтения, записи и т.д.).

2. Режимы открытия файлов
При открытии файлов необходимо указывать режим:
- 'r' - чтение.
- 'w' - запись.
- 'a' - добавление строки.

3. with
Использование with при открытии файлов является хорошей практикой, так как:
- Гарантирует, что файл будет закрыт автоматически после завершения блока, даже если возникло исключение.

4. Работа с текстами
Работа с текстовой информацией включает:
- Учет кодировок (например, utf-8), что особенно важно при работе с данными на разных языках.
- Обработка строк: методами strip(), split(), join() и другими, для манипуляций со строками.
