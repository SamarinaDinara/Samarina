# Samarina
## Задание 1

Скачала виртуальную машину и гостевые дополнения (рис. 1).

![изображение](https://github.com/user-attachments/assets/0e7b99b7-024b-493a-adf6-fe1cabbe3b2f)

Рисунок 1 - ВМ и гостевые дополнения

Прописала следующую команду (рис. 2):
```
sudo yum install wget
```

- sudo — это команда, которая позволяет выполнять другие команды с правами суперпользователя (администратора). Это необходимо, когда операция требует повышенных привилегий, например, установка программного обеспечения на уровне системы.
- yum (Yellowdog Updater, Modified) — это пакетный менеджер, используемый в системах на базе Red Hat, таких как CentOS, RHEL (Red Hat Enterprise Linux), Fedora и других. Он отвечает за управление пакетами: установку, удаление, обновление и поиск программного обеспечения из репозиториев.
- install — это аргумент для yum, который указывает, что нужно установить указанный пакет. В данном случае команда говорит пакетному менеджеру найти и установить программу.
- wget — это утилита командной строки, предназначенная для загрузки файлов из интернета. Она поддерживает различные протоколы, такие как HTTP, HTTPS и FTP, и может работать в фоновом режиме, продолжая загрузку даже при разрыве соединения.

![изображение](https://github.com/user-attachments/assets/e803929b-59b7-4e20-a0de-218052417082)

Рисунок 2 - wget

## Задание 2

Прописала команду (рис. 1):
```
sudo yum install curl
```

- sudo — предоставляет права суперпользователя (администратора). Это необходимо для выполнения операций, требующих повышенных привилегий, таких как установка программного обеспечения.
- yum — это пакетный менеджер, используемый в системах на базе Red Hat (например, CentOS, RHEL, Fedora). Он автоматически обрабатывает зависимости между пакетами и загружает необходимые файлы из репозиториев.
- Аргумент install указывает yum, что нужно установить указанный пакет (curl в данном случае).
- curl — это мощная утилита командной строки для передачи данных через различные протоколы, такие как HTTP, HTTPS, FTP, SMTP и другие.

![изображение](https://github.com/user-attachments/assets/4ef29603-2c28-444a-a674-a465afc8f6e6)

Рисунок 1 - curl

Прописала команду (рис. 2):
```
sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo
```

- sudo предоставляет права суперпользователя (администратора). Это необходимо, так как директория /etc/yum.repos.d/ требует повышенных привилегий для записи.
- wget — это утилита командной строки, предназначенная для загрузки файлов из интернета. Она поддерживает различные протоколы, такие как HTTP, HTTPS и FTP.
- -P /etc/yum.repos.d/
  - Опция -P указывает целевую директорию, куда будет сохранён загруженный файл.
  - В данном случае файл будет сохранён в /etc/yum.repos.d/.
- URL: https://download.docker.com/linux/centos/docker-ce.repo — Это адрес файла, который нужно скачать. В данном случае это конфигурационный файл репозитория Docker Community Edition (CE) для CentOS.

![изображение](https://github.com/user-attachments/assets/8ea76c6f-5095-464d-ae87-4194b4a50d67)

Рисунок 2 - Docker

Прописала команду (рис. 3):
```
sudo yum install docker-ce docker-ce-cli containerd.io
```

- sudo предоставляет права суперпользователя (администратора). Это необходимо для выполнения операций, требующих повышенных привилегий, таких как установка программного обеспечения.
- yum — это пакетный менеджер, используемый в системах на базе Red Hat (например, CentOS, RHEL, Fedora). Он автоматически обрабатывает зависимости между пакетами и загружает необходимые файлы из репозиториев.
- install — указывает yum, что нужно установить указанные пакеты.
- docker-ce — это основной пакет Docker Community Edition. Он содержит саму программу Docker, которая позволяет запускать контейнеры, управлять образами и взаимодействовать с Docker Hub.
- docker-ce-cli — это пакет, содержащий командную строку Docker (CLI). Этот инструмент предоставляет интерфейс для управления Docker через терминал (например, команды docker run, docker ps, docker build и т.д.).
- containerd.io — это отдельный компонент, который управляет контейнерами на низком уровне. Он является частью экосистемы Docker и используется для запуска и управления контейнерами.

![изображение](https://github.com/user-attachments/assets/679ba852-9a15-4f19-8d10-91cc5085fbc7)

Рисунок 3 - Компоненты для Docker

Прописала команду (рис. 4):
```
sudo systemctl enable docker --now
```

- sudo предоставляет права суперпользователя (администратора). Это необходимо для выполнения операций управления системными службами.
- systemctl — это утилита для управления системными службами в Linux. Она позволяет запускать, останавливать, перезапускать, включать автозапуск и выполнять другие действия с сервисами.
- Аргумент enable указывает systemctl, что нужно настроить автозапуск службы Docker при загрузке системы. Это создаст соответствующие символические ссылки в конфигурации systemd.
- Флаг --now добавляет дополнительное действие: немедленный запуск службы Docker, если она ещё не запущена. То есть команда выполняет сразу два действия:
  - Включает автозапуск службы.
  - Запускает службу прямо сейчас.

![изображение](https://github.com/user-attachments/assets/cfb91d9d-0521-47b0-b554-89fce89b0bff)

Рисунок 4 - Автозапуск

## Задание 3
