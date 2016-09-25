# until

Тело оператора `until` выполняется до тех пор, пока условие не станет *truthy*. Проще говоря, `until` это просто синтаксический сахар для оператора `while` с противоположным условием:

```crystal
until some_condition
  do_this
end

# То же, что и:
while !some_condition
  do_this
end
```

В теле `until` можно также использовать инструкции `break` и `next`.
