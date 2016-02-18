# На RedHat и CentOS

TODO: В RedHay получена дистрибьюция, вы можете использовать официальный Crystal репозиторий.(In RedHat derived distributions, you can use the official Crystal repository.)

## Настройка репозитория

Сначала вы должны добавить репозиторий в YUM конфигурацию. Для этого просто запустите в командной строке:

```
  curl http://dist.crystal-lang.org/rpm/setup.sh | sudo bash
```

Это добавит ключ подписи и конфигурацию репозитория. Если вы хотите сделать это вручную, выполните:

```
rpm --import http://dist.crystal-lang.org/rpm/RPM-GPG-KEY

cat > /etc/yum.repos.d/crystal.repo <<END
[crystal]
name = Crystal
baseurl = http://dist.crystal-lang.org/rpm/
END
```

## Установка
После того, как ваш репозиторий сконфигурирован, вы можете установить Crystal:

```
sudo yum install crystal
```

## Обновление

После выхода новой версии Crystal, вы можете обновить его в системе:

```
sudo yum update crystal
```
