# Подготовка сервера =
## Установка DE ==
```
sudo apt-get install \
    xfce4 \
    xfce4-goodies \
    xorg \
    dbus-x11 \
    x11-xserver-utils \
    ranger \
    neovim \
    git \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
sudo apt-get install language-pack-ru
sudo update-locale LANG=ru_RU.UTF-8
```

## Установка x2goServer
```
sudo apt-get install x2goserver x2goserver-xsession
```

## Добавить пользователя ==
```
sudo adduser efremov
sudo gpasswd -a efremov sudo
```

### Скопировать ключь авторизации
cat ~/.ssh/id_rsa.pub | ssh efremov@88.99.192.234 'cat >> ~/.ssh/authorized_keys'

### Установка Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

### Установка образа 1с
psql -U postgres -d template1 -c "ALTER USER postgres PASSWORD 'password'"
