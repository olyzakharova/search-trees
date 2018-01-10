# search-trees

## Сравнение двух структур данных: красно-черного дерева (RBtree) и 2-3-дерева (23tree).
-------------------
## Список источников:
1. Томас Кормен, Чарльз Лейзерсон, Рональд Риверст, Клиффорд Штайн "Алгоритмы. Построение и анализ. Третье издание"
2. Ключарев П.Г. "Дополнительные главы дискретной математики: Алгоритмы и структуры данных"
3. http://cplusplus.kurttest.com
4. http://cs.wellesley.edu/~cs230/fall04/2-3-trees.pdf
5. http://cs.wellesley.edu/~cs231/fall01/red-black.pdf



### ПРИМЕЧАНИЕ: Тесты test1,test2,test3,test4,test5 написаны к обеим структурам данных. 
### Тесты test23_1-test23_4 и testRB1-testRB4 показывают, что программа и ее методы работают корректно.

# Входной файл с командами может содержать следующие команды:

***add [key]*** ***[data]***

***delete [key]***

***print***

***search [key]***

***max***

***min***

***(где key, data - целые числа)***

# Оценка сложности алгоритмов:
## Для 2-3-дерева:
1.	Вставка.
    Так как мы спускаемся один раз, и поднимаемся вверх при расщеплении родителей не более одного раза, то вставка работает за **O(log n)**;
2.	Поиск имеет сложность **O(log n)**;
3.	Удаление имеет сложность **O(log n)**.

## Для красно-черного дерева:
1.	Вставка имеет сложность **O(log n)**;
2.	Удаление имеет сложность **O(log n)**.
3.	Поиск имеет сложность **O(log n)**;

### НО

1.	Красно-черное дерево удаляет быстрее, хотя в 2-3-дереве при удалении количество подъемов не ограничено.
2.	Красно-черное дерево занимает меньше памяти.

# Сравнение:
 
В первой строке создаем дерево и поместили в него 1024 * 1024 элементов. 

Во второй строке мы по очереди ищем в дереве каждый из этих элементов.

В третьей строке удаляем из дерева по одному элементу.

# Результаты сравнения:
 
##  Для отсортированной последовательности:

2-3 tree:

Creation of tree with 1048576 nodes took **390** ms

Finding all nodes took **191** ms

Deletion of all nodes took **198** ms

Red-Black tree:

Creation of tree with 1048576 nodes took **210** ms

Finding all nodes took **71** ms

Deletion of all nodes took **153** ms


Исходя из этих данных можно сделать вывод, что: 
1. Вставка проходит быстрее в красно-черном дереве.
2. Поиск проходит быстрее в красно-черном дереве.
3. Удаление проходит быстрее в красно-черном дереве.


##  Для частично отсортированной последовательности:

2-3 tree:

Creation of tree with 1048576 nodes took **634** ms

Finding all nodes took **135** ms

Deletion of all nodes took **237** ms

Red-Black tree:

Creation of tree with 1048576 nodes took **494** ms

Finding all nodes took **117** ms

Deletion of all nodes took **207** ms


Исходя из этих данных можно сделать вывод, что: 
1. Вставка проходит быстрее в красно-черном дереве.
2. Поиск проходит быстрее в красно-черном дереве.
3. Удаление проходит быстрее в красно-черном дереве.


##  Для неотсортированной последовательности:

2-3 tree:

Creation of tree with 1048576 nodes took **1160** ms

Finding all nodes took **209** ms

Deletion of all nodes took **289** ms

Red-Black tree:

Creation of tree with 1048576 nodes took **1044** ms

Finding all nodes took **195** ms

Deletion of all nodes took **291** ms


Исходя из этих данных можно сделать вывод, что: 
1. Вставка проходит быстрее в красно-черном дереве.
2. Поиск проходит быстрее в красно-черном дереве.
3. Удаление проходит быстрее в 2-3-дереве.


#### Следует заметить, что разница не особо велика, так что теоретические ожидания почти подтвердились.

# Описание команды `print`:
Для красно-черного дерева:  при выводе в файл рядом с красными вершинами пишется (red), выводятся ключи в порядке возрастания индексов по уровням.

Для 2-3-дерева: выводятся ключи в порядке возрастания индексов по уровням.

Например: 

2-3 tree:

Insert 'A':

└──  A

Insert 'L':

└──  A|L

Insert 'G':

└──  G

     ├──  L
     
     └──  A
     


Insert 'O':

└──  G

     ├──  L|O
     
     └──  A


