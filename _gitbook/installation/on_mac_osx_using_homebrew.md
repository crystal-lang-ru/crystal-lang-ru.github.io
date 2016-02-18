# На Mac OSX используя Homebrew

Для более простой установки, вы можете использовать [Homebrew](http://brew.sh/).

```
brew update
brew install crystal-lang
```

Если вы планируете учавствовать в проекте, то вам может пригодится LLVM. Также замените последнюю строку:
(If you're planning to contribute to the project you might find useful to install LLVM as well. So replace the last line with:)

```
brew install crystal-lang --with-llvm
```

## Исправление проблем на OSX 10.11 (El Capitan)

Если вы получили такую ошибку:

```
ld: library not found for -levent
```

TODO: Вам нужно переустановить инструменты командной строки и выбрать активный набор инструментов по умолчанию:
(you need to reinstall the command line tools and then select the default active toolchain:)

```
$ xcode-select --install
$ xcode-select --switch /Library/Developer/CommandLineTools
```
