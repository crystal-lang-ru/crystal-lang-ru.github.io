# sizeof

Выражение `sizeof` возращает `Int32` с размером переданного типа в байтах. Для примера:

```crystal
sizeof(Int32)  #=> 4
sizeof(Int64)  #=> 8
```

Для [ссылочных](http://crystal-lang.org/api/Reference.html) типов размер типа аналогичен размеру указателя:

```crystal
# На 64-битных машинах
sizeof(Pointer(Int32)) #=> 8
sizeof(String)         #=> 8
```

Так потому, что память зарезервирована в куче и передается указатель на нее. Что бы получить действительный размер класса, используйте [instance_sizeof](instance_sizeof.html).

Аргумент для sizeof это [тип](type_grammar.html), поэтому sizeof часто используют в комбинации с [typeof](typeof.html):

```crystal
a = 1
sizeof(typeof(a)) #=> 4
```
