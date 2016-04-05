# Множественное присваивание

Вы можете объявить несколько переменных одновременно, разделяя выражения запятой (`,`):

```crystal
name, age = "Crystal", 1

# то же, что и:
temp1 = "Crystal"
temp2 = 1
name  = temp1
age   = temp2
```

Обратите внимание, так как выражения присваиваются временным переменным, можно обменять содержимое переменных в одну строку:

```crystal
a = 1
b = 2
a, b = b, a
a #=> 2
b #=> 1
```

Если правая часть содержит только одно выражение, то оно будет считаться индексным:

```crystal
name, age, source = "Crystal,1,github".split(",")

# то же, что и:
temp = "Crystal,1,github".split(",")
name   = temp[0]
age    = temp[1]
source = temp[2]
```

Если левая часть содержит одну переменную, то правая часть будет считаться массивом:

```crystal
names = "John", "Peter", "Jack"

# то же, что и:
names = ["John", "Peter", "Jack"]
```

Множественное присваивание также доступно для методов, которые оканчиваются на `=`:

```crystal
person.name, person.age = "John", 32

# то же, что и:
temp1 = "John"
temp2 = 32
person.name = temp1
person.age = temp2
```

А также доступно индексным выражениям (`[]=`):

```crystal
objects[1], objects[2] = 3, 4

# то же, что и:
temp1 = 3
temp2 = 4
objects[1] = temp1
objects[2] = temp2
```
