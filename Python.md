# New monent for me about
## Ternary condition
* Ternary - syntactic construction, which allows compact print  conditional expression.
```
<value_if _condition_true >if<condition>else<value_if_condition_false>
```
Именованные аргументы в Python — это аргументы, которые передаются не просто как значения, а как пара «имя=значение». Их можно перевавать в любом порядке.

Причины использовать именованные аргументы:

Они повышают читаемость, так как сразу видно имена.

Можно не указывать все промежуточные параметры, которые сейчас не нужны. Это полезно, если у функции много необязательных параметров.

Именованные аргументы можно передавать одновременно с позиционными. Тогда позиционные должны идти в самом начале. 34:17 урок 8
## .Methods
* <u>.format</u>  
*This method replaced in 'str' what is writen in brackets the fact the in it (in the same order) *
```
print('We are the {} who say "{}!"'.format('knights', 'Ni'))
#We are the knights who say "Ni!"
```
# Interesting tasks for course

##   Task1
Винни-Пух попросил Вас посмотреть, есть ли в его стихах ритм. Поскольку разобраться в его кричалках не настолько просто, насколько легко он их придумывает, Вам стоит написать программу.
Винни-Пух считает, что ритм есть, если число слогов (т.е. число гласных букв) в каждой фразе стихотворения одинаковое.
Фраза может состоять из одного слова, если во фразе несколько слов, то они разделяются дефисами.
Фразы отделяются друг от друга пробелами.
Стихотворение  Винни-Пух передаст вам автоматически в переменную stroka в виде строки. В ответе напишите Парам пам-пам, если с ритмом все в порядке и Пам парам, если с ритмом все не в порядке.
Если фраза только одна, то ритм определить не получится и необходимо вывести: Количество фраз должно быть больше одной!.

## My solution

*I decided that me shold print one function which be do all. I use anly simple constructions and three cycles. This code long, ugly and not convenient*

```
stroka = 'за-гад-ка-ра-свет-ка-ра-газ-да-не-на-ма-ли-ва-ла'
def Vini(array):
    list=[]
    vowels="ауеоыяию"
    list=stroka.split()
    if len(list)<=1:
        print("Количество фраз должно быть больше одной!")
        return exit
    Tern=0
    befor=0
    tf=True
    for i in list:
        for j in i:
            for o in vowels:
                if str(j)==o:
                    Tern+=1
        if befor!=Tern and  befor!=0:
            tf=False
        befor=Tern
        Tern=0
    if tf== True:
        print("Парам пам-пам")
    else:
        print("Пам парам")

Vini(stroka)
```
## GB solution
1. *This solution also use method "split" and "else" instead of "exit".*
2. *They use method ***count*** instead of  my construction "if-else" in cycles.*
3.  GB use ***list generator*** instead of two of my cycles. It made the code more readable. 
```
vowels = ['а', 'е', 'ё', 'и', 'й', 'о', 'у', 'ы', 'э', 'ю', 'я']
phrases = stroka.split()
if len(phrases) < 2:
 print('Количество фраз должно быть больше одной!')
else:
 countVowels = []

 for i in phrases:
  countVowels.append(len([x for x in i if x.lower() in vowels]))

 if countVowels.count(countVowels[0]) == len(countVowels):
  print('Парам пам-пам')
 else:
  print('Пам парам')
```
***.count*** - method, which defines quantity elements with specified value in array.  

<u><span style="font-size:17px;">Сonclusion:</span></u> Me shuld use **list generators** more because it faster than cycle 'for' and code looks more loconically and beautifully.

## Task2
Напишите функцию print_operation_table(operation, num_rows, num_columns), которая принимает в качестве аргумента функцию, вычисляющую элемент по номеру строки и столбца. По умолчанию номер столбца и строки = 9.
Аргументы num_rows и num_columns указывают число строк и столбцов таблицы, которые должны быть распечатаны.
Нумерация строк и столбцов идет с единицы (подумайте, почему не с нуля).
Если строк меньше двух, выдайте текст
ОШИБКА! Размерности таблицы должны быть больше 2!.
Примечание: бинарной операцией называется любая операция, у которой ровно два аргумента, как, например, у операции умножения.
Между элементами должен быть 1 пробел, в конце строки пробел не нужен.

## My solution
```
def print_operation_table(operation, num_rows=9, num_columns=9):
    if num_rows<=2 or num_columns<=2:
        print("ОШИБКА! Размерности таблицы должны быть больше 2!")
        return exit
    Tern=""
    for i in range(1,num_rows+1):
        for j in range(1,num_columns+1):
            Tern+=str(operation(i,j))
            if j!=num_columns:
                Tern+=" "
        print(Tern,sep='\n')
        Tern=""

#print_operation_table(lambda x, y: x * y, 5, 3)
```
## GB solution 
1. *GB use construction 'if-else' instead of 'exit'*
2. *In their solution they use 'array' (set) data type instead of **str** (i use it becouse str is special case of set)*
3. _They use constructions ***f'{}***  and append moveing the next line with the help method 'append' and give it in array_ 
4. They use ***list generator*** for print set and method ***join*** 

```
def print_operation_table(operation, num_rows=9, num_columns=9):
    result = []
    if num_rows < 2 or num_columns < 2:
        print('ОШИБКА! Размерности таблицы должны быть больше 2!')
    else:
        for i in range(1, num_rows + 1):
            for j in range(1, num_columns + 1):
                if j != num_columns :
                    result.append(f'{operation(i, j)} ')
                else:
                    result.append(operation(i, j))
            result.append('\n')
        print(''.join([str(i) for i in result[:len(result) - 1]]))
```

***f'{}*** - constructions  
***.join*** - method, which transform ***interatad object*** in string and divides his objects with specific pointer (back to the metod *.split*)  
***interatad object*** - object which capable of elements at one at time (for example array or set)