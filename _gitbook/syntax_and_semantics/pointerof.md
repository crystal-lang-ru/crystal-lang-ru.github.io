# pointerof

Выражение `pointerof` возвращает [Указатель](http://crystal-lang.org/api/Pointer.html), который указывает на содержимое переменной или экземпляр переменной.

Пример с переменной:

```crystal
a = 1

ptr = pointerof(a)
ptr.value = 2

a #=> 2
```

Пример с экземпляром переменной:

```crystal
class Point
  def initialize(@x, @y)
  end

  def x
    @x
  end

  def x_ptr
    pointerof(@x)
  end
end

point = Point.new 1, 2

ptr = point.x_ptr
ptr.value = 10

point.x #=> 10
```

Так как `pointerof` содержит указатели, то он считается [небезопасным](unsafe.html).

