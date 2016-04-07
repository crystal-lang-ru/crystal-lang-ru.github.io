# Псевдонимы

Используя 'alias' вы можете указать для типа другое имя:

```crystal
alias PInt32 = Pointer(Int32)

ptr = PInt32.malloc(1) # : Pointer(Int32)
```

Каждый раз, когда вы используете псевдоним, компилятор заменяет его на тот тип, на который он ссылается.

Псевдонимы хороши для избежания слишком длинных имен, но так же могут ссылаться на рекурсивные типы:

```crystal
alias RecArray = Array(Int32) | Array(RecArray)

ary = [] of RecArray
ary.push [1, 2, 3]
ary.push ary
ary #=> [[1, 2, 3], [...]]
```

Реальный пример использования рекурсивного типа - это json:

```crystal
module Json
  alias Type = Nil |
               Bool |
               Int64 |
               Float64 |
               String |
               Array(Type) |
               Hash(String, Type)
end
```
