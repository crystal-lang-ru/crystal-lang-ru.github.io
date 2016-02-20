# HTTP сервер

Немного более интересным примером является HTTP сервер:

```crystal
require "http/server"

server = HTTP::Server.new(8080) do |context|
  context.response.content_type = "text/plain"
  context.response.print "Hello world! The time is #{Time.now}"
end

puts "Listening on http://0.0.0.0:8080"
server.listen
```

Приведенный код выше будет иметь смысл только если вы прочитаете всю документацию, но вы уже можете кое-чему научиться.

* Вы можете [подключить](../syntax_and_semantics/requiring_files.html) код из других файлов:

    ```ruby
    require "http/server"
    ```
* Вы можете определить [локальную переменную](../syntax_and_semantics/local_variables.html) без необходимости указывать ее тип:

    ```ruby
    server = HTTP::Server.new ...
    ```

* Ваша программа вызывает [методы](../syntax_and_semantics/classes_and_methods.html) (или посылает сообщения) объектам.

    ```ruby
    HTTP::Server.new(8000) ...
    ...
    Time.now
    ...
    puts "Listening on http://0.0.0.0:8080"
    ...
    server.listen
    ```

* Вы можете использовать блоки кода, или просто [блоки](../syntax_and_semantics/blocks_and_procs.html), которые представляют собой очень удобный способ повторного использования кода и дают возможность получить некоторые особенности из мира функционального программирования:

    ```ruby
    HTTP::Server.new(8080) do |context|
      ...
    end
    ```

* Вы легко можете создавать строки со "встроенным" контентом, который также называется интерполяция строк. Язык также предоставляет другой [синтаксис](../syntax_and_semantics/literals.html) для создания arrays(массивов), hashes(хэшей), ranges(диапазонов), tuples(тьюплов/кортежей) и прочего:

    ```ruby
    "Hello world! The time is #{Time.now}"
    ```
