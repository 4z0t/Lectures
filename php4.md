# Экосистема php

## Конфигурирование

Базовая настройка происходит через файл `php.ini`

Синтаксис:

*имя_настройки* = *значение_параметра*

Пример:

extension=php_curl.dll
disable_functions=...
disable_classes=...

date.timezone=Europe/Moscow

memory_limit=128M

## Обработка ошибок

display_errors=Off
error_reporting=E_ALL & ~E_DEPRECATED
log_errors=On

...

## Ограничение ресурсов

max_execution_time=30
max_input_vars=1000

## Загрузка файлов

file_uploads
upload_max_filesize

## Модули

Интерпретатор состоит из ядра и подключаемых модулей.

* Массивы
* Классы и объекты
* Дата/Время
* Обработка ошибок

## Установка

...

### Opcache

Используется для оптимизации исполняемого кода путем компиляции напрямую в байткоды (опкоды).

### JIT компиляция

Анализирует какой сгенерированный код, чтобы затем решать какой код *стоит* компилировать, а какой нет.

### Apcu

Хранилище "ключ-значение". Ключи - строки, значения - любые переменные.

### Redis

* отдельная программа - хранилище данных, используемое в качестве базы данных, кэша, брокера сообщений.

### cURL

* библиотека, позволяющая взаимодействовать с множеством сервером посредством различных протоколов.

### FTP

Функции для работы с серверами FTP.

### PDO

PHP Data Objects - интерфейс для доступа к базам данных php.

### XDebug

Отладчик/профайлер php

## Пакеты php

Классы и функции, написанные на php. Поставляются через пакетный менеджер.

### Pear

Официальная библиотека пакетов php.

## Composer

Современный пакетный менеджер.

### Консольные команды

## Стандартные рекомендации

## Подключение классов без автозагрузки

Подключаем каждый класс через require_once

## Автозагрузка

Функция для автозагрузки

## Monolog

