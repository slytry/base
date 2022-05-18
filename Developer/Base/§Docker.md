---
aliases: null
date created: {{date:YYYY-MM-DD}} {{time:HH:mm}}
date updated:
---


### Для чего?
Решает проблему когда на одной машине все работает, а на другой нет

### Прокси
Для каждого проекты создается отдельное локальное доменное имя.

Для того чтобы работать с множеством локальных доменных имен необходим механизм локального проксирующего сервера.

Таковым будет является [nginx-proxy](https://git.chulakov.org/docker/compose-base/developer-env/nginx-proxy). Предназначение у него одно — пропускать (проксировать) запросы по 80-ому порту локальной машины до соответствующего контейнера с нужным приложением.

Для того чтобы локальные доменные имена работали, необходимо сказать операционной системе, что это доменное имя соотнесено с локальным хостом (127.0.0.1).


### Две сети

Все докер контейнеры будут работать в двух локальный сетях

**одна сеть — внешняя сеть, в которой работает основной прокси-сервер, некоторые вспомогательные сервисы и веб-серверы уровня проекта. Эта сеть будет обозначаться всегда переменной окружения FRONTEND_NETWORK_NAME в ваших .env-файлах. И, по умолчанию, иметь значение proxy-network**

**Вторая сеть — это сеть, в которой работают основные контейнеры уровня приложений ваших проектов. Например, контейнеры c php-fpm. Эта сеть будет обозначаться всегда переменной окружения BACKEND_NETWORK_NAME в ваших .env-файлах. И, по умолчанию, иметь значение applications-network.**

**

Тут надо скачать докер

```
$ docker network create proxy-network

$ docker network create applications-network

```

### Запуск основного прокси-сервера

- Перейдем в папку, где будут храниться наши репозитории с Docker-окружением, а не реальными проектами.
- Далее, клонируем сюда проект с [nginx-proxy](https://git.chulakov.org/docker/compose/developement/nginx-proxy) и запустим его без изменений:

```
$ git clone ssh://git@git.chulakov.org:2222/docker/compose/developement/nginx-proxy.git

$ cd ./nginx-proxy

$ docker-compose up -d

```


### Запуск Portainer

[Portainer](https://www.portainer.io/) — это средство мониторинга Docker-окружения и средство управления практически всеми объектами Docker-экосистемы у вас на локальной машине. Здесь вы сможете просматривать и анализировать запущенные контейнеры, существующие сети, хранящиеся у вас образы и прочее. Принцип запуска [этого сервиса](https://git.chulakov.org/docker/compose/developement/portainer) схож с nginx-proxy:



```

$ git clone ssh://git@git.chulakov.org:2222/docker/compose-base/developer-env/portainer.git

$ cd ./portainer

$ docker-compose up -d

```



---

###### Citation
https://docs.google.com/document/d/1yOvQCxe69lnAKaheTLv-cbO2HXJsxCckSg_SQB6Yw-Y/edit#heading=h.p1p8b6q8twxc

YT:

-  [Docker: глубокое погружение (плейлист)](https://www.youtube.com/watch?v=v_GbcTpMTLE&list=PLvTBThJr861x2qFBVwOlqIrbaft-Im-0u)
-  [Docker Tutorial for Beginners](https://www.youtube.com/watch?v=0N3n56KsC28&list=PLZTsCOAKJJ_YZglqBYyrRx_iy_npQH-3N&index=2&t=133s)