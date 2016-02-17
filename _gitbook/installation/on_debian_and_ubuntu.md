# На Debian и Ubuntu

TODO: В Debian получена дистрибьюция, вы можете использовать официальный Crystal репозиторий.(In Debian derived distributions, you can use the official Crystal repository.)

## Настройка репозитория

Сначала вы должны добавить репозиторий в APT конфигурацию. Для этого просто запустите в командной строке:

```
  curl http://dist.crystal-lang.org/apt/setup.sh | sudo bash
```

Это добавит ключ подписи и конфигурацию репозитория. Если вы хотите сделать это вручную, выполните:

```
apt-key adv --keyserver keys.gnupg.net --recv-keys 09617FD37CC06B54
echo "deb http://dist.crystal-lang.org/apt crystal main" > /etc/apt/sources.list.d/crystal.list
```

## Установка
После того, как ваш репозиторий сконфигурирован, вы можете установить Crystal:

```
sudo apt-get install crystal
```

## Обновление

После выхода новой версии Crystal, вы можете обновить его в системе:

```
sudo apt-get update
sudo apt-get install crystal
```
