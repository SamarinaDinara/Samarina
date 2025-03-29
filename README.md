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
- URL: `https://download.docker.com/linux/centos/docker-ce.repo` — Это адрес файла, который нужно скачать. В данном случае это конфигурационный файл репозитория Docker Community Edition (CE) для CentOS.

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

Прописала команду (рис. 1):
```
COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)
```

- Запрашивает данные о последнем релизе Docker Compose через GitHub API.
- Извлекает из ответа значение поля tag_name (номер версии).
- Сохраняет номер версии в переменную COMVER.
Пример результата: COMVER="v2.20.2".

![изображение](https://github.com/user-attachments/assets/40c49f05-46a5-4c89-a898-6a40cd412f3e)

Рисунок 1 - Получает номер последней версии Docker Compose из GitHub

Прописала команду (рис. 2):
```
sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
```

- curl -L
  - curl — это утилита для загрузки файлов из интернета.
  - -L указывает curl автоматически следовать перенаправлениям (например, если ссылка ведет на другой URL).
- `"https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)"`
  - $COMVER: переменная, содержащая номер версии Docker Compose (например, v2.20.2).
  - $(uname -s): команда, возвращающая название операционной системы (например, Linux).
  - $(uname -m): команда, возвращающая архитектуру процессора (например, x86_64).
- -o /usr/bin/docker-compose
  - -o указывает, куда сохранить загруженный файл.
  - /usr/bin/docker-compose — это путь, куда будет сохранён бинарный файл Docker Compose. Директория /usr/bin/ обычно находится в переменной PATH, что позволяет запускать Docker Compose из любой директории.

![изображение](https://github.com/user-attachments/assets/a40d94e8-3228-4b5f-88b4-0206229d6875)

Рисунок 2 - Скачивание бинарного файла

Прописала команду (рис. 3):
```
sudo chmod +x /usr/bin/docker-compose
```

- chmod — это утилита для изменения прав доступа к файлам и директориям.
- +x - Флаг +x добавляет атрибут "исполняемый" (execute) для файла. Это позволяет запускать файл как программу или скрипт.
- /usr/bin/docker-compose - Это путь к файлу, который был скачан ранее (например, бинарный файл Docker Compose). После выполнения этой команды файл станет исполняемым.

![изображение](https://github.com/user-attachments/assets/3bfba4ba-04d9-499c-8279-bd58ca7d21df)

Рисунок 3 - Подготовка Docker-compose

Прописала команду (рис. 4):
```
docker-compose --version
```

- Команда узнаёт версию Docker-compose

![изображение](https://github.com/user-attachments/assets/2ab97683-1da7-4d8f-9c03-cffb8cdd6e07)

Рисунок 4 - Версия

Прописала команду (рис. 5):
```
sudo yum install git
```

- git — это распределённая система контроля версий, которая используется для отслеживания изменений в файлах и координации работы над проектами. Она широко применяется в разработке программного обеспечения, особенно в сочетании с платформами, такими как GitHub, GitLab и Bitbucket.

![изображение](https://github.com/user-attachments/assets/e60ab238-10bf-42f3-88a8-d4c4297e431b)

Рисунок 5 - Установка git

Прописала команду (рис. 6):
```
git clone https://github.com/skl256/grafana_stack_for_docker.git
```

- git clone — это команда Git, которая используется для создания локальной копии удалённого репозитория. Она загружает все файлы и историю изменений из указанного URL.
- `https://github.com/skl256/grafana_stack_for_docker.git` - Это URL удалённого репозитория на GitHub. В данном случае репозиторий называется grafana_stack_for_docker, и он принадлежит пользователю skl256.

![изображение](https://github.com/user-attachments/assets/9c7f9699-27aa-4362-a924-aad2d29ff3ab)

Рисунок 6 - Установка директории

Прописала команду (рис. 7):
```
cd grafana_stack_for_docker
```

- Переход в директорию grafana_stack_for_docker

![изображение](https://github.com/user-attachments/assets/c9830d37-dfcb-4796-8f65-c81a91da3c47)

Риунок 7 - grafana_stack_for_docker

Прописала команду (рис. 8):
```
sudo mkdir -p /mnt/common_volume/swarm/grafana/config
```

- mkdir — это утилита для создания директорий (папок) в Linux.
- -p - Флаг -p указывает mkdir создавать не только указанную директорию, но и все необходимые родительские директории, если они ещё не существуют.
- /mnt/common_volume/swarm/grafana/config - Это полный путь к директории, которую нужно создать.

![изображение](https://github.com/user-attachments/assets/e617a74b-41e3-40fa-b3c5-c374debee1ac)

Рисунок 8 - Создание директории

Прописала команду (рис. 9):
```
sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}
```

- mkdir -p
  - mkdir — это утилита для создания директорий.
  - Флаг -p указывает mkdir, что нужно создать все необходимые родительские директории, если они ещё не существуют. Если какая-либо из родительских директорий уже существует, команда просто проигнорирует её.
-  `/mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}` - Это путь к директориям, которые нужно создать. Синтаксис {} используется для создания нескольких директорий одновременно:
  - grafana-config
  - grafana-data
  - prometheus-data

![изображение](https://github.com/user-attachments/assets/9fc03782-7135-44df-bff2-aed9c5d94f90)

Рисунок 9 - Создание ещё нескольких директорий

Прописала команду (рис. 10):
```
sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}
```

- chown — это утилита для изменения владельца и/или группы файлов и директорий.
- -R - Флаг -R (рекурсивный) указывает, что изменения должны применяться ко всем файлам и поддиректориям внутри указанных директорий.
- $(id -u):$(id -g) -Это команда, которая динамически определяет текущего пользователя и его группу:
  - id -u: возвращает ID текущего пользователя.
  - id -g: возвращает ID основной группы текущего пользователя.
- {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} - Это список директорий, к которым применяется команда. Используется синтаксис фигурных скобок {}, чтобы указать несколько путей:
  - /mnt/common_volume/swarm/grafana/config
  - /mnt/common_volume/grafana

![изображение](https://github.com/user-attachments/assets/39ed9fc7-a6f9-420d-9461-8f30564539de)

Рисунок 10 - Группа директорий

Прописала команду (рис. 11):
```
touch /mnt/common_volume/grafana/grafana-config/grafana.ini
```

- touch -  Утилита touch используется для создания пустых файлов или обновления временных меток существующих файлов.
  - Если файл /mnt/common_volume/grafana/grafana-config/grafana.ini не существует, он будет создан.
  - Если файл уже существует, его содержимое останется без изменений, но временная метка (timestamp) будет обновлена.
- /mnt/common_volume/grafana/grafana-config/grafana.ini :
  - Это полный путь к файлу, который нужно создать или обновить.
  - В данном случае файл grafana.ini будет создан в директории /mnt/common_volume/grafana/grafana-config/.

![изображение](https://github.com/user-attachments/assets/074703a9-4ee0-4094-a1d1-be5ea879ce67)

Рисунок 11 - Файл

Прописала команду (рис. 12):
```
cp config/* /mnt/common_volume/swarm/grafana/config/
```

- cp — это утилита для копирования файлов и директорий.
- config/*
  - config/ — это путь к исходной директории, из которой нужно скопировать файлы.
  - * — это подстановочный символ (wildcard), который означает "все файлы" в указанной директории.
- /mnt/common_volume/swarm/grafana/config/- Это путь к целевой директории, куда будут скопированы файлы.

![изображение](https://github.com/user-attachments/assets/e8760fa5-b555-4110-9363-1a4362ce1185)

Рисунок 12 - Копирование файлов

Прописала команду (рис. 13):
```
mv grafana.yaml docker-compose.yaml
```

- mv — это утилита для перемещения или переименования файлов и директорий.
- grafana.yaml - Это исходный файл, который нужно переименовать.
- docker-compose.yaml - Это новое имя файла, которое будет присвоено после выполнения команды.

![изображение](https://github.com/user-attachments/assets/ef122e25-cbfe-432a-aeec-7273f1081ad6)

Рисунок 13 - Новое имя у файла

Прописала команду (рис. 14):
```
sudo docker compose up -d
```

- docker compose — это команда Docker, которая используется для работы с сервисами, описанными в файле docker-compose.yaml. Она позволяет запускать, останавливать и управлять несколькими контейнерами одновременно.
- Аргумент up указывает Docker Compose запустить все сервисы, описанные в файле docker-compose.yaml. Если контейнеры ещё не созданы, они будут созданы, а затем запущены.
- Флаг -d (detached mode) указывает, что контейнеры должны быть запущены в фоновом режиме. Это означает, что терминал не будет "заблокирован" выводом логов контейнеров, и вы сможете продолжать использовать его для других задач.

![изображение](https://github.com/user-attachments/assets/0491e3bd-7eb4-4032-85a3-5b0013d87f38)

Рисунок 14 - Поднятие docker-compose

## Задание 4

Прописала команду (рис. 1):
```
sudo docker compose up -d
```

- Эта команда поднимает docker-compose в фоновом режиме, перед этим следует перейти в директорию grafana_stack_for_docker.

![изображение](https://github.com/user-attachments/assets/a0b43fbf-adab-4912-956c-e7612cd8a355)

Рисунок 1 - Docker-compose

Прописала команду (рис. 2):
```
sudo docker compose stop
```

- Аргумент stop указывает Docker Compose остановить все запущенные контейнеры, связанные с текущим файлом docker-compose.yaml. Контейнеры будут остановлены "мягко", то есть Docker отправит сигнал SIGTERM (завершение работы), а затем, если контейнер не завершится за определённое время (по умолчанию 10 секунд), отправит SIGKILL (принудительное завершение).

![изображение](https://github.com/user-attachments/assets/b105d8e6-21e7-44cf-ae36-66f410164b43)

Рисунок 2 - Остановка docker-compose

Прописала команду (рис. 3):
```
sudo docker compose down
```


- Аргумент `down` указывает Docker Compose выполнить следующие действия:
  - Остановить все запущенные контейнеры .
  - Удалить контейнеры , связанные с текущим файлом docker-compose.yaml.
  - Удалить сети , созданные для этих контейнеров.

![изображение](https://github.com/user-attachments/assets/24f4cfd1-6c02-4f38-81f4-af1af37f4b78)

Рисунок 3 - Остановка docker-compose

Прописала команду (рис. 4):
```
sudo docker compose ps
```

- Аргумент ps (process status) указывает Docker Compose вывести список всех контейнеров, связанных с текущим проектом, и их текущее состояние.

![изображение](https://github.com/user-attachments/assets/46a45278-0f1b-45b0-8ea5-7cedc6c85734)

Рисунок 4 - Состояние контейнеров

Прописала команду (рис. 5):
```
git clone https://github.com/SamarinaDinara/Samarina.git
```

- git clone — это команда Git, которая используется для создания локальной копии удалённого репозитория. Она загружает все файлы и историю изменений из указанного URL.
- `https://github.com/SamarinaDinara/Samarina.git` - Это URL удалённого репозитория на GitHub. В данном случае репозиторий называется Samarina, и он принадлежит пользователю SamarinaDinara.

![изображение](https://github.com/user-attachments/assets/5bd17ecf-3c2f-45b4-9fea-90c984b94939)

Рисунок 5 - Копирование файлов из моего репозитория

Прописала команду (рис. 6):
```
pwd
```

- Утилита pwd используется для отображения абсолютного пути текущей директории.

![изображение](https://github.com/user-attachments/assets/fb9b68d1-fe2a-47d1-96de-85002b38727c)

Рисунок 6 - Полный путь

Прописала следующую команду (рис. 7):
```
mv Samarina/docker-compose.yaml ./
```

- mv — это утилита для перемещения или переименования файлов и директорий.
- Samarina/docker-compose.yaml - Это исходный путь к файлу, который нужно переместить. В данном случае файл docker-compose.yaml находится в директории Samarina/.
- ./ - Это целевой путь, куда будет перемещён файл.

![изображение](https://github.com/user-attachments/assets/602237f9-d070-4ea2-aa8d-9cab449a8a6e)

Рисунок 7 - Бэкап docker-compose и перенос нового

Прописала следующую команду (рис. 8):
```
mv Samarina/prometheus.yaml /mnt/common_volume/swarm/grafana/config/
```

- Samarina/prometheus.yaml - Это исходный путь к файлу, который нужно переместить. В данном случае файл prometheus.yaml находится в директории Samarina/.
- /mnt/common_volume/swarm/grafana/config/ - Это целевой путь, куда будет перемещён файл. Файл будет помещён в директорию /mnt/common_volume/swarm/grafana/config/.

![изображение](https://github.com/user-attachments/assets/9c1623bf-4de0-4dab-8f0a-2a8e0303aa49)

Рисунок 8 - Перенос prometheus

## Задание 5

Зашла на сайт по адресу `localhost:3000`, перед этим подняв docker-compose (рис. 1). Вписала данные:

- Логин: admin
- Пароль: admin

![изображение](https://github.com/user-attachments/assets/0dc93b8d-0a37-45b1-9de3-f18c7c7c5f44)

Рисунок 1 - Сайт Grafana

Создала новую data source с данными (рис. 2). После нажала Save & Test.

- Connection: http://prometheus:9090
- Authentication: Basic authentication

![изображение](https://github.com/user-attachments/assets/0610bdcc-4369-4cfa-bb57-fcdc1860ed69)

Рисунок 2 - Data source

Всё это было сделано для того, чтобы создать новую Dashboard (рис. 3).

![изображение](https://github.com/user-attachments/assets/24086b0e-abd8-4841-9a24-ed5d122205fb)

Рисунок 3 - Dashboard

## Задание 6

Создала новую DATA SOURCE с ссылкой `http//:victoriametrics:8428` (рис. 1).

![изображение](https://github.com/user-attachments/assets/583175ea-3a0c-46e1-8040-46ff0fcb332b)

Рисунок 1 - Виктория Метрик

Прописала команду (рис. 2):

```
echo -e "# TYPE light_metric1 gauge\nlight_metric1 0" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus
```

Эта команда отправляет метрику в формате Prometheus в сервис, работающий на `localhost:8428` (VictoriaMetrics).

1. **`echo -e "# TYPE light_metric1 gauge\nlight_metric1 0"`**:
   - Создает текст в формате Prometheus exposition format:
     - `# TYPE light_metric1 gauge` — указывает, что метрика `light_metric1` имеет тип `gauge`.
     - `light_metric1 0` — значение метрики равно `0`.

2. **`| curl --data-binary @-`**:
   - Передает этот текст через pipe (`|`) в команду `curl`.
   - `--data-binary @-` означает, что данные берутся из стандартного ввода (то есть из `echo`) и отправляются "как есть" (без изменений).

3. **`http://localhost:8428/api/v1/import/prometheus`**:
   - URL-адрес, куда отправляются данные. Это endpoint для импорта метрик в формате Prometheus.

![изображение](https://github.com/user-attachments/assets/95989281-5913-422e-af10-b684981dbca0)

Рисунок 2 - Отправка метрики

После создала новый Dashboard с созданным DATA SOURCE (victoria), и получила результат после использования команды (рис. 3).

![изображение](https://github.com/user-attachments/assets/bf9955ae-58e0-406e-86eb-88ad9c7b05ab)

Рисунок 3 - Новый dashboard

Вписала следующие команды, для выстраивание графика (рис. 4):

```
echo -e "# TYPE light_metric1 gauge\nlight_metric1 100" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus
```


```
echo -e "# TYPE light_metric1 gauge\nlight_metric1 50" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus
```


```
echo -e "# TYPE light_metric1 gauge\nlight_metric1 75" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus
```

![изображение](https://github.com/user-attachments/assets/f1cff0cd-1d11-4eff-b54e-0d7234aeac3d)

![изображение](https://github.com/user-attachments/assets/7398f865-c0ff-4e30-82a9-25d05f70ab4f)

Рисунок 4 - График и команды

Следующее, что я сделал, это связала график с 0 и моими данными, после чего сохранила Dashboard (рис. 5).

![изображение](https://github.com/user-attachments/assets/0f0c9f2b-b988-449b-9a7a-b7bc372b674d)

![изображение](https://github.com/user-attachments/assets/54cdcc78-fca3-488a-996e-23509fef3312)

Рисунок 5 - Готовый dashboard
