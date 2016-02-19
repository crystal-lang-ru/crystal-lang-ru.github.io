# Tuple

[Tuple](http://crystal-lang.org/api/Tuple.html) (Кортеж) обычно создается с помощью литерала кортежа:

```crystal
tuple = {1, "hello", 'x'} # Tuple(Int32, String, Char)
tuple[0]                  #=> 1       (Int32)
tuple[1]                  #=> "hello" (String)
tuple[2]                  #=> 'x'     (Char)
```

Для создания пустого кортежа используйте [Tuple.new](http://crystal-lang.org/api/Tuple.html#new%28%2Aargs%29-class-method).
