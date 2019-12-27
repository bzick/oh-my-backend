# Oh My BackEnd

Пункты выствлены в порядке удобства их изучения. Метка `[pro]` означает что этот пункт для более глубокого изучения темы и можно пропустить если хочется.

Каждый пункт надо знать как с этим работать и для чего. Как это работает будет дополнительным бустом в изучении пункта.

* Виртуализация docker
  * установить [docker](https://www.docker.com/products/docker-desktop)
  * запустить контейнер с Linux Ubuntu, последней LTS версией. Запустить bash контейнера.
  * установить удобное приложение для урпавления образами и контейнерами [Kitematic](https://kitematic.com/), [Portainer](https://hub.docker.com/r/portainer/portainer/) и тд. Либо сродниться с консольными командами docker
  * compose будет позже
* Linux
  * Установка пакетов через apt/apt-get/aptitude
  * Базовые навыки в bash
    * Базовый синтаксис bash
      * for
      * if
      * Логические `;`, `&&`, `||`
    * Базовые команды ls, find, cat, top/htop
    * Команды обработки данных tail, head, sed, grep, awk
    * Консольные редакторы vim/vi, nano. Откыть файл, внести изменения, сохранить.
    * Консольный просмоторщик less. Открыть, найти слово, закрыть.
    * Конвееры команд через `|` (`cmd1 | cmd2`)
    * Фоновые задачи, оператор `&`, команды `fg`, `bg`
  * Понятие 'процесс'
    * Мастер-воркер процессы, демон (daemon)
    * Дочерний процесс, воркер
    * Зомби процесс 
    * [Отправка сигналов процессам](https://ru.wikipedia.org/wiki/Сигнал_(Unix))
      * Изучение команды kill, pkill, killall
      * Назначение сигналов [SIGKILL](https://ru.wikipedia.org/wiki/SIGKILL), [SIGTERM](https://ru.wikipedia.org/wiki/SIGTERM), [SIGINT](https://ru.wikipedia.org/wiki/SIGTERM), [SIGHUP](https://ru.wikipedia.org/wiki/SIGHUP), [SIGSEGV](https://ru.wikipedia.org/wiki/SIGSEGV)
    * Команада анализа работы процесса через strace
  * Изучение понятия 'дескриптор'
    * Стандартные дескрипторы STDIN, STDOUT, STDERR
    * Ограничение на дескрипторы
    * Потоки, сокеты и unix-сокеты
    * Команада анализа открытых дескрипторов у процесса через lsof
  * Права и доступы файловой системы
    * Супер пользователь, команды `su` и `sudo`
    * Флаги доступов x, r, w (что они значат для файлов и директорий)
    * Понимание описания доступов вида `--xr-xrwx` у файлов и директорий
    * Изменение прав доступов через команды chmod, chown
  * Исполняемые файлы
    * [sha bang](https://ru.wikipedia.org/wiki/Шебанг_(Unix))
  * Запуск и остановка сервисов systemd
  * [SSH](https://ru.wikipedia.org/wiki/SSH)
    * Генерация собственного ssh-rsa ключа
    * Использование публичного ssh-rsa ключа для входа на удалённую машину (используйте второй контейнер с linux).
  * Планировщик crond/crontab
* Общие знания
  * Регулярные выражения. Поиграться регулярными выражениями можно [тут](https://regex101.com/).
  * Хеш функции, в том числе `crc32`, `md5`, `sha1`. Цифровые подписи, соль для подписей, коллизии хешей.
  * Базовая работа с git
    * комит изменений (commit)
    * отправка изменений (push/pull)
    * создание веток и тега (branch/tag)
  * Стуктуры хранения данных
    * Хеш таблицы
    * Очередь и стек
    * [Связный список](https://ru.wikipedia.org/wiki/Связный_список) и [двусвязный список](https://ru.wikipedia.org/wiki/Связный_список#Двусвязный_список_(двунаправленный_связный_список))
  * Форматы хранения данных
    * JSON
    * YAML
    * XML
* Сеть
  * Базовое понимание работы сети, протокл TCP и протокл UDP.
  * IPv4, IPv6
  * DNS
  * Трассировки маршрутов.
  * `[pro]` анализ трафика через tcpdump + wireshark
* Базы данных
  * SQL базы данных MySQL/Postgres/итд
    * Базовый синтаксис запросов SELECT/INSERT/UPDATE/DELETE
    * Типы колонок таблиц их назначение их различие (на примере MySQL и схожих)
      * tinyint/smallint/int/bigint
      * tinytext/text/mediumtext/longtext
      * set/enum
      * char/varchar
      * decimal
      * double
      * прочие
    * Анализ выполнения запросов через EXPLAIN, понимание результатов EXPLAIN.
    * [Понимание работы индексов](https://ruhighload.com/Индексы+в+mysql)
      * Назначение PRIMARY индексов
      * Назначение UNIQUE/обычный индексов
      * Составные индексы.
        * Понимание какие поля в какой последовательности добавлять в индекс при фиьтрации и сортировке одновременно.
      * `[pro]` Алгоритм построения индексов BTREE
     * Объединение таблиц LEFT JOIN, RIGHT JOIN, INNER JOIN, OUTER JOIN, JOIN
     * Группировка данных через GROUP BY
       * Фильтрация после группировки
       * Функции работы с группами MAX/MIN/AVG/итд
     * Понимание и назначение внешних ключей (`foreign key`)
     * 
  * noSQL базы данных MongoDB/DocumentDB
  * Redis
    * базовая работа с ключами
    * работа со списками
    * работа с хешами
    * работа с набором и сортированным набором
    * `[pro]` Алгоритм хранения [skip List](https://ru.wikipedia.org/wiki/Список_с_пропусками)
* Протокол HTTP
  * [Понимание общего формата протокола](https://developer.mozilla.org/ru/docs/Web/HTTP/Overview): где заголовки, а где тело.
  * Сродниться со вкладкой Сеть/Network в инспекторе браузера, где можно наблюдать HTTP запросы.
  * [Методы HTTP запросов](https://developer.mozilla.org/ru/docs/Web/HTTP/Methods).  Их назначение и ограничения.
    * Основные [GET](https://developer.mozilla.org/ru/docs/Web/HTTP/Methods/GET), [POST](https://developer.mozilla.org/ru/docs/Web/HTTP/Methods/POST), [HEAD](https://developer.mozilla.org/ru/docs/Web/HTTP/Methods/HEAD)
    * Прочие `PUT`, `DELETE` итд.
  * [Коды HTTP ответов](https://ru.wikipedia.org/wiki/Список_кодов_состояния_HTTP)
    * Основные (частые): 200, 301, 302, 304, 400, 401, 403, 404, 500, 502, 503, 504
    * Другие
  * Заголовки HTTP запроса
    * Системные заголовоки Host, Content-Type, Content-Length
    * [Кеширование HTTP](https://developer.mozilla.org/ru/docs/Web/HTTP/%D0%9A%D1%8D%D1%88%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5) и изучение HTTP заголовков упарвления кешом Cache-Control, Expires, Vary, ETag, Last-Modified
  * [Куки](https://developer.mozilla.org/ru/docs/Web/HTTP/%D0%9A%D1%83%D0%BA%D0%B8)
  * Различия версий протокола HTTP/1.0, HTTP/1.1 
  * Тело HTTP запроса
    * Формат передачи `application/x-www-form-urlencoded`
    * Формат передачи [multipart/form-data](https://ru.wikipedia.org/wiki/Multipart/form-data)
    * Влияние заголовков (Content-Length, [Content-Encoding](https://developer.mozilla.org/ru/docs/Web/HTTP/Headers/Content-Encoding), [Transfer-Encoding](https://developer.mozilla.org/ru/docs/Web/HTTP/Headers/Transfer-Encoding)) на тело 
  * `[pro]` HTTP/2.0 протокол
  * `[pro]` WebSocket протокол
  * HTTP API
    * [REST API](https://ru.wikipedia.org/wiki/REST)
    * `[pro]` [GraphQL](https://habr.com/ru/post/326986/)
* Web сервер [NGINX](https://nginx.org/ru/)
  * [Ознакомление с базовыми возможностями](https://nginx.org/ru/docs/beginners_guide.html) 
  * Написание простых локаций в `/etc/nginx/nginx.conf`
