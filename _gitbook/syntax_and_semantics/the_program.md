# Программа

Программа — это глобальный объект, в котором вы можете определить типы, методы и файловые локальные переменные.

```crystal
# Определение метода в программе
def add(x, y)
  x + y
end

# Вызов метода add в программе
add(1, 2) #=> 3
```

Значение метода — значение последнего вычисленного в нём выражения, поэтому нет необходимости явно использовать `return`. Однако явно использовать `return` возможно:

```crystal
def even?(num)
  if num % 2 == 0
    return true
  end

  return false
end
```

When invoking a method without a receiver, like `add(1, 2)`, it will be searched in the program if not found in the current type or any of its ancestors.
Если вызвать метод без получателя, например `add(1, 2)`, и его не окажется в текущем типе или в любом из его предков, он будет искаться в программе:

```crystal
def add(x, y)
  x + y
end

class Foo
  def bar
    # Вызов программного метода add
    add(1, 2)

    # Вызов метода baz класса Foo
    baz(1, 2)
  end

  def baz(x, y)
    x * y
  end
end
```

Если вам необходимо вызвать программный метод, даже если в текущем типе определён метод с таким же именем, используйте префикс `::`:

```crystal
def baz(x, y)
  x + y
end

class Foo
  def bar
    baz(4, 2) #=> 2
    ::baz(4, 2) #=> 6
  end

  def baz(x, y)
    x - y
  end
end
```

Объявленные в программе переменные недоступны из методов:

```crystal
x = 1

def add(y)
  x + y # error: undefined local variable or method 'x'
end

add(2)
```

Использование скобок при вызове метода не обязательно:

```crystal
add 1, 2 # То же, что и add(1, 2)
```

## Основной код

Основной код, — код, запускаемый при компиляции и выполнении программы, может быть записан прямо в исходном файле. Оборочивать его в метод "main" нет необходимости:

```crystal
# Эта программа выводит "Hello Crystal!"
puts "Hello Crystal!"
```

Основной код также может быть внутри объявлений типа:

```crystal
# Эта программа выводит "Hello"
class Hello
  # здесь 'self' это класс Hello
  puts self
end
```
