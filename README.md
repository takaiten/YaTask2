# Задача 'B' из цикла задач Яндекса для стажировки


|Ограничение времени|3 секунды|
|---|---|
|**Ограничение памяти**|256Mb|
|**Ввод**|стандартный ввод или input.txt|
|**Вывод**|стандартный вывод или output.txt|

Есть база данных телефонных номеров. Необходимо для каждого номера определить страну, оператора, а также привести номер в определённый формат. 

Существует список шаблонов, которым может удовлетворять номер. Он имеет вид: **NUMBER - COUNTRY OPERATOR**

+ NUMBER – шаблон номера, формат ниже 
+ COUNTRY – названия страны, последовательности символов латинского алфавита 
+ OPERATOR – названия оператора, последовательности символов латинского алфавита и цифр 
    
Номер в шаблоне задаётся в следующем виде: **+COUNTRY_CODE (OPERATOR_CODE) PERSONAL_NUMBER**

+ COUNTRY_CODE – код страны, от одной до трёх цифр, первая цифра не может быть нулём 
+ OPERATOR_CODE – код оператора, от двух до четырёх цифр 
+ PERSONAL_NUMBER – шаблон номера абонента внутри оператора, строка длиной от пяти до девяти символов. Символом может быть цифра от 0 до 9 или символ X. Символ X означает, что на данной позиции может быть любая цифра от 0 до 9. Справа от символа X не может стоять цифра 

Все номера телефонов в текущей базе данных содержатся в полном формате (все цифры присутствуют), но, в отличие от формата выше: 
+ могут отсутствовать знак + и скобки 
+ могут отсутствовать или быть в любом месте номера пробелы и знак-разделитель дефис 
+ не содержат больше никакой информации (имени абонента, оператора и т.п.) 
    
Гарантируется, что для каждого номера существует ровно один шаблон, которому он удовлетворяет, и все шаблоны не пересекаются. 

## Формат ввода
Первая строка содержит число N (1≤N≤1000) – количество номеров в базе данных. 
Далее следует N строк – номера телефонов по одному номеру в строке. Длина строки не превосходит 100 символов. 
Следующая строка содержит число M (1≤M≤1000) – количество шаблонов. 
Далее M строк – шаблоны в формате, описанном выше. Длина шаблона не превосходит 100 символов. 
## Формат вывода
Выведите N строк, в каждой номер в новом формате в том порядке, в котором они указаны во входе. 
## Примечания
Некоторые страны могут иметь одинаковый **COUNTRY_CODE**.
### Пример 1
|Ввод|Вывод|
|---|---|
|4|+28 (495) 1234567 - ElDorado GoldLine
|28-49-5-123-45-67|+875 (44) 456789 - Atlantis MobTelecom
|87544456789|+28 (495) 1234556 - ElDorado GoldLine
|+28 (495) 123 45 56|+875 (29) 123456 - Atlantis MythCell
|875-(29)-123456
|3
|+875 (29) 1XXXXX - Atlantis MythCell
|+875 (44) 4XXXXX - Atlantis MobTelecom
|+28 (495) XXXXXXX - ElDorado GoldLine

### Пример 2
|Ввод|Вывод|
|---|---|
|2|+1 (23) 45678 - Canada AnotherCell
|12345678|+1 (234) 56789 - USA SomeCell
|123456789
|2
|+1 (234) XXXXX - USA SomeCell
|+1 (23) XXXXX - Canada AnotherCell
