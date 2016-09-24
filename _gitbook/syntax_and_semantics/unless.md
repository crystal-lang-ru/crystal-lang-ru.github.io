# unless

Оператор `unless` выполняет ветку `then` если условие *falsey*, в противном случае выполняет ветку `else`. Можно сказать, он действует как `if`, но наоборот:

```crystal
unless some_condition
  then_expression
else
  else_expression
end

# То же, что и:
if some_condition
  else_expression
else
  then_expression
end

# Можно записать как суффикс
close_door unless door_closed?
```
