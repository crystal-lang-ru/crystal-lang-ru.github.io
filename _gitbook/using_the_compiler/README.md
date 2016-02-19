# Работа с компилятором

После [установки](../installation/README.md) компилятора `crystal` в вашем распоряжении.

В следующих разделах знак доллар (`$`) обозначает командную строку.

## Компиляция и моментальное выполнение

Скомпилировать и запустить программу вы можете набрав `crystal` с именем файла:

```
$ crystal some_program.cr
```

Файлы исходного кода Crystal имеют расширение `.cr`.

Альтернативой может служить команда `run`:

```
$ crystal run some_program.cr
```

## Создание исполняемого файла

Используйте команду `build` чтобы создать исполняемый файл:

```
$ crystal build some_program.cr
```

Это создаст `some_program` файл, который можно выполнить:

```
$ ./some_program
```

**Примечание:** По умолчанию сгенерированные файлы **не полностью оптимизированы**. Чтобы включить полную оптимизацию, используйте флаг `--release`:

```
$ crystal build some_program.cr --release
```

Всегда используйте флаг `--release` для готовых к продакшену исполняемых файлов и для проведения бенчмарков.

Причиной этому является то, что производительность без полной оптимизации довольно хорошая и обеспечивает быстрое время компиляции, так что вы можете использовать команду `crystal` как будто это интерпретатор.

## Создание проекта или библиотеки

Используйте команду `init` чтобы создать Crystal проект со стандартной структурой директорий.

```
$ crystal init lib MyCoolLib
      create  MyCoolLib/.gitignore
      create  MyCoolLib/LICENSE
      create  MyCoolLib/README.md
      create  MyCoolLib/.travis.yml
      create  MyCoolLib/shard.yml
      create  MyCoolLib/src/MyCoolLib.cr
      create  MyCoolLib/src/MyCoolLib/version.cr
      create  MyCoolLib/spec/spec_helper.cr
      create  MyCoolLib/spec/MyCoolLib_spec.cr
Initialized empty Git repository in ~/MyCoolLib/.git/
```

## Другие команды и опции

Чтобы посмотреть полный список команд, наберите `crystal` без аргументов.

```
$ crystal
Usage: crystal [command] [switches] [program file] [--] [arguments]

Command:
    init                     generate new crystal project
    build                    compile program file
    deps                     install project dependencies
    docs                     generate documentation
    eval                     eval code from args or standard input
    run (default)            compile and run program file
    spec                     compile and run specs (in spec directory)
    tool                     run a tool
    --help, -h               show this help
    --version, -v            show version
```

Чтобы увидеть доступные параметры для каждой команды, используйте флаг `--help` после команды:

```
$ crystal build --help
Usage: crystal build [options] [programfile] [--] [arguments]

Options:
    --cross-compile flags            cross-compile
    -d, --debug                      Add symbolic debug info
    -D FLAG, --define FLAG           Define a compile-time flag
    --emit [asm|llvm-bc|llvm-ir|obj] Comma separated list of types of output for the compiler to emit
    -h, --help                       Show this message
    --ll                             Dump ll to .crystal directory
    --link-flags FLAGS               Additional flags to pass to the linker
    --mcpu CPU                       Target specific cpu type
    --no-color                       Disable colored output
    --no-codegen                     Don't do code generation
    -o                               Output filename
    --prelude                        Use given file as prelude
    --release                        Compile in release mode
    -s, --stats                      Enable statistics output
    --single-module                  Generate a single LLVM module
    --threads                        Maximum number of threads to use
    --target TRIPLE                  Target triple
    --verbose                        Display executed commands
```
