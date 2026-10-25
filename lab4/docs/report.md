# Отчёт по лабораторной работе № 4

## 1. Цель работы

Изучить возможности платформы n8n для автоматизации процессов, освоить создание и настройку workflow, работу с различными узлами, а также взаимодействие с Redis через Docker.

## 2. Выполненная работа

В ходе лабораторной работы была установлена и настроена платформа n8n. Были созданы и проверены workflow для выполнения различных задач:

- Создание и обработка данных с помощью узлов Manual Trigger, Set и Code.
- Использование JavaScript в узле Code для обработки данных, переменных, массивов и объектов.
- Реализация условного ветвления с помощью узла IF.
- Формирование и обработка данных с использованием узла Set.
- Получение данных из внешнего API с помощью HTTP Request.
- Настройка автоматического запуска workflow с помощью Schedule Trigger.
- Запуск Redis в Docker и подключение его к n8n.
- Создание, чтение, удаление и проверка существования ключей Redis.
- Настройка туннелирования с помощью Tailscale Funnel для предоставления внешнего доступа к локальному экземпляру n8n, запущенному в Docker.

Для подтверждения выполнения заданий были сделаны скриншоты установки, настройки и результатов выполнения workflow.

## 3. Использованные узлы n8n

В процессе выполнения лабораторной работы были освоены следующие узлы:

| **Узел** | **Назначение** |
|---|---|
| Manual Trigger | Ручной запуск workflow |
| Set | Создание и изменение данных |
| Code | Выполнение JavaScript-кода и обработка данных |
| IF | Условное ветвление workflow |
| HTTP Request | Отправка HTTP-запросов и получение данных из API |
| Schedule Trigger | Автоматический запуск workflow по расписанию |
| Redis Set | Создание и сохранение ключа и значения в Redis |
| Redis Get | Чтение значения по ключу Redis |
| Redis Delete | Удаление ключа Redis |
| Redis Exists | Проверка существования ключа Redis |

## 4. Скриншоты выполненных заданий

### 4.1. Установка и настройка n8n

[Установка n8n](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/01-n8n-installed.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/01-n8n-installed.png)

*Рисунок 1 — Установка n8n.*

[Вход в n8n](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/02-logged-in-n8n.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/02-logged-in-n8n.png)

*Рисунок 2 — Успешный вход в n8n.*

### 4.2. Создание и обработка данных

[Workflow 1](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-01-manual-set-code.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-01-manual-set-code.png)

*Рисунок 3 — Workflow Manual Trigger → Set → Code.*

[Workflow 2](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-02-code.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-02-code.png)

*Рисунок 4 — Использование JavaScript в узле Code.*

[Workflow 3](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-03-if.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-03-if.png)

*Рисунок 5 — Условное ветвление с помощью IF.*

[Workflow 4](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-04-set-node.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-04-set-node.png)

*Рисунок 6 — Создание и обработка данных с помощью Set.*

### 4.3. Работа с HTTP Request и расписанием

[Workflow 5](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-05-http-request.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-05-http-request.png)

*Рисунок 7 — Получение данных из внешнего API с помощью HTTP Request.*

[Workflow 6](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-06-schedule.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-06-schedule.png)

*Рисунок 8 — Автоматический запуск workflow с помощью Schedule Trigger.*

### 4.4. Работа с Redis

[Workflow 9](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-09-redis.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-09-redis.png)

*Рисунок 9 — Создание и чтение ключа Redis.*

[Workflow 10](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-10-redis.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-10-redis.png)

*Рисунок 10 — Удаление ключа и проверка его существования.*

[Workflow 10 execution](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-10-redis-executed.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-10-redis-executed.png)

*Рисунок 11 — Результат выполнения workflow удаления ключа Redis.*

### 4.5. Публикация n8n с помощью Tailscale Funnel

Для предоставления внешнего доступа к локальному экземпляру n8n был настроен туннель с использованием Tailscale Funnel.

n8n был запущен в Docker и доступен локально по адресу `http://localhost:5678`. Для публикации сервиса была использована команда PowerShell:

```powershell
tailscale funnel 5678
```

После запуска команды Tailscale Funnel предоставил публичный HTTPS-адрес, через который можно получить доступ к локальному экземпляру n8n из внешней сети.

Работоспособность туннеля была проверена путём открытия полученной публичной ссылки в браузере. Таким образом, был изучен способ предоставления внешнего доступа к локально запущенному веб-приложению без непосредственного изменения конфигурации n8n.

Публичный туннель использовался для демонстрации работы приложения. После завершения проверки туннель можно остановить с помощью `Ctrl+C` в окне PowerShell.

[Workflow 12](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-12-proof-of work-tailscale.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-12-proof-of-work-tailscale.png)

*Рисунок 12 — Подтверждение настройки туннелирования с помощью Tailscale Funnel.*

[Workflow 13](https://github.com/eanzgaard/visual-programming-labs-zimens/blob/main/lab4/screenshots/flow-13-proof-of-work-tailscale.png) ([image](https://github.com/eanzgaard/visual-programming-labs-zimens/raw/main/lab4/screenshots/flow-13-proof-of-work-tailscale.png)

*Рисунок 13 — Подтверждение доступности n8n через публичный адрес Tailscale Funnel.*

## 5. Выводы

В ходе лабораторной работы я изучил основы работы с n8n и научился создавать workflow для автоматизации различных процессов.

Я освоил основные узлы платформы, научился обрабатывать данные с помощью JavaScript, выполнять условное ветвление, получать информацию из внешних API и запускать процессы по расписанию.

Также я изучил взаимодействие n8n с Redis. С помощью Docker был запущен Redis, после чего я создал ключ, прочитал его значение, удалил ключ и проверил, что он больше не существует.

Дополнительно я изучил принцип туннелирования с помощью Tailscale Funnel и получил практический опыт предоставления внешнего доступа к локальному веб-приложению, запущенному в Docker.

В результате лабораторной работы я получил практические навыки создания и настройки workflow, которые могут использоваться для автоматизации обработки данных и взаимодействия с внешними сервисами.