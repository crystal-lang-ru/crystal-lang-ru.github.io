# if

`if` выполняет  ветку `then` если условие *truthy* (сводится к true), в противном случае выполняет ветку `else`.

```crystal
a = 1
if a > 0
  a = 10
end
a #=> 10

b = 1
if b > 2
  b = 10
else
  b = 20
end
b #=> 20
```

Чтобы написать цепочку условий, используйте `elsif`:

```crystal
if some_condition
  do_something
elsif some_other_condition
  do_something_else
else
  do_that
end
```

После выполнения `if` тип переменной будет зависеть от типа выражений в каждой из ветвей.

```crystal
a = 1
if some_condition
  a = "hello"
else
  a = true
end
# a : String | Bool

b = 1
if some_condition
  b = "hello"
end
# b : Int32 | String

if some_condition
  c = 1
else
  c = "hello"
end
# c : Int32 | String

if some_condition
  d = 1
end
# d : Int32 | Nil
```

Обратите внимание, что если в одной из ветвей не будет указан тип переменной, после выполнения `if` он будет содержать тип `Nil`.

В теле оператора `if` переменная будет того типа, который назначается в данной ветке. Если тип не был переназначен, он останется прежним:


```crystal
a = 1
if some_condition
  a = "hello"
  # a : String
  a.size
end
# a : String | Int32
```

Иначе говоря, тип переменной будет определяться последним выражением, назначившим его.

Если одна из ветвей не достигает конца оператора `if`, например, в случае использования `return`, `next`, `break` или `raise`, определяемый ей тип не будет назначен переменной после выхода из тела `if`:

```crystal
if some_condition
  e = 1
else
  e = "hello"
  # e : String
  return
end
# e : Int32
```
