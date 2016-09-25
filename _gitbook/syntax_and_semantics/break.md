# break

Чтобы прервать выполнение цикла `while`, вы можете воспользоваться `break`:

```crystal
a = 2
while (a += 1) < 20
  if a == 10
    # перейдёт к 'puts a'
    break
  end
end
puts a #=> 10
```
