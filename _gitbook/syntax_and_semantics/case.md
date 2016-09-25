# case

`case` — управляющее выражение, которое в некотором роде проверяет на соответствие шаблону. Оно позволяет писать цепочки условий с минимальными изменениями в семантике и использовать более мощные конструкции.

В общем случае оно сопоставляет одно значение с рядом других значений.

```crystal
case exp
when value1, value2
  do_something
when value3
  do_something_else
else
  do_another_thing
end

# То же, что и:
tmp = exp
if value1 === tmp || value2 === tmp
  do_something
elsif value3 === tmp
  do_something_else
else
  do_another_thing
end
```

Обратите внимание, что `===` используется для сравнения, аналогичного сравнению в операторе `case`.

Если в выражении `when` указан тип, в аналогичной конструкции `if` используется `is_a?`. Кроме того, если выражение `case` — переменная или присваивание значения переменной, тип переменной будет ограничен:

```crystal
case var
when String
  # var : String
  do_something
when Int32
  # var : Int32
  do_something_else
else
  # здесь переменная var не String и не Int32
  do_another_thing
end

# То же, что и:
if var.is_a?(String)
  do_something
elsif var.is_a?(Int32)
  do_something_else
else
  do_another_thing
end
```

Вы можете вызвать метод выражения `case` в выражении `when` использовав синтаксис неявного объекта:

```crystal
case num
when .even?
  do_something
when .odd?
  do_something_else
end

# То же, что и:
tmp = num
if tmp.even?
  do_something
elsif tmp.odd?
  do_something_else
end
```

А ещё вы можете пренебречь значением `case`:

```crystal
case
when cond1, cond2
  do_something
when cond3
  do_something_else
end

# То же, что и:
if cond1 || cond2
  do_something
elsif cond3
  do_something_else
end
```

Порой так можно сделать код ближе к человеческому языку.
