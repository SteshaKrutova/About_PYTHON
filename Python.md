# New monent for me about

# Interesting tasks for course

##   Task1
Винни-Пух попросил Вас посмотреть, есть ли в его стихах ритм. Поскольку разобраться в его кричалках не настолько просто, насколько легко он их придумывает, Вам стоит написать программу.
Винни-Пух считает, что ритм есть, если число слогов (т.е. число гласных букв) в каждой фразе стихотворения одинаковое.
Фраза может состоять из одного слова, если во фразе несколько слов, то они разделяются дефисами.
Фразы отделяются друг от друга пробелами.
Стихотворение  Винни-Пух передаст вам автоматически в переменную stroka в виде строки. В ответе напишите Парам пам-пам, если с ритмом все в порядке и Пам парам, если с ритмом все не в порядке.
Если фраза только одна, то ритм определить не получится и необходимо вывести: Количество фраз должно быть больше одной!.

## My walking

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
## GB walking
1. *This wolking also use method "split" and "else" instead of "exit".*
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
***count*** - method, which defines quantity elements with specified value in array.  