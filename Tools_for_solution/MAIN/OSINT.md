
## **Maltego**
### Описание

**Maltego** — это мощная платформа для **Open Source Intelligence (OSINT)** и графического анализа связей (link analysis). Инструмент позволяет визуализировать сложные отношения между сущностями: людьми, компаниями, доменами, IP-адресами, email, социальными сетями, инфраструктурой интернета и другими данными из публичных источников. Maltego использует **Transforms** (преобразования) — автоматизированные запросы к различным базам данных, API и источникам (более 150 встроенных и тысячи от партнёров), чтобы собирать и связывать информацию в интерактивный граф. Это один из ведущих инструментов для пентестеров, аналитиков угроз, журналистов, следователей и специалистов по кибербезопасности. Разработан компанией Maltego Technologies (ранее Paterva), работает на Java, кросс-платформенный (Windows, macOS, Linux).

### Версии Maltego (на начало 2026 года)

Maltego эволюционировал от классических редакций (Community, Classic, XL) к новой модели на основе **Maltego Graph**:

- **Community Edition (CE)** / **Basic Plan** — бесплатная версия с регистрацией Maltego ID. Ограничения: до 24 результатов на Transform, доступ к базовым данным через Maltego Data Pass, подходит для обучения и личного использования.
- **Pro Plan** — платная, полный доступ к коммерческим данным, больше кредитов на запросы, продвинутые Machines (автоматизация).
- **Enterprise Plan** — для команд и организаций: неограниченные запросы, интеграция внутренних данных, серверные возможности. Последняя версия клиента **Maltego Graph** — **4.8.x** (с 2025 года CaseFile интегрирован в CE; обновления выходят регулярно, проверяйте changelog на сайте).

### Основные инструменты

- **Transforms** → Автоматизированные запросы к источникам (DNS, Whois, Shodan, социальные сети, breach databases, Dark Web и т.д.). Доступны через **Transform Hub** — маркетплейс с интеграциями от 35+ партнёров.
- **Entities** → Сущности (Person, Domain, IP Address, Phone Number, Email, Location и custom).
- **Graph** → Интерактивная визуализация связей с разными layouts (organic, hierarchical и т.д.).
- **Machines** → Автоматизированные цепочки Transforms для типичных сценариев (например, "Company Stalker" или "Find Wikipedia Edits").
- **Data Integrations** → Более 150 стандартных + партнёрские (например, IPQualityScore, BuiltWith, urlscan.io).
- **Maltego Data Pass** → Доступ к коммерческим OSINT-данным (включая в бесплатный план ограниченно).

### Ссылка для скачивания

Официальная страница загрузки: **[https://www.maltego.com/downloads/](https://www.maltego.com/downloads/?referrer=grok.com)**

Для Community Edition: Зарегистрируйтесь на сайте (Maltego ID), затем скачайте клиент. Требуется Java 11 или 17. Для Kali Linux и подобных — часто предустановлен, но для свежей версии используйте официальный сайт.



## **theHarvester**
### Описание

**theHarvester** — это мощный инструмент для сбора открытой разведывательной информации (**OSINT** — Open Source Intelligence). Он предназначен для пассивной разведки на этапе reconnaissance в penetration testing или red team assessments. Инструмент собирает email-адреса, субдомены, хосты, IP-адреса, виртуальные хосты, имена сотрудников, открытые порты, баннеры и URL, связанные с целевым доменом или компанией. theHarvester использует множество публичных источников (поисковые системы, базы сертификатов, Shodan и т.д.), поддерживает API-ключи для расширенных запросов и позволяет обходить ограничения. Это один из стандартных инструментов в Kali Linux для картирования внешней атаки поверхности организации.

### Версии theHarvester (на начало 2026 года)

Активно развиваемый open-source проект на GitHub. На начало января 2026 года последняя версия — **4.8.2** (как указано в выводе инструмента в Kali Linux). Обновления выходят регулярно: добавляются новые источники данных, улучшения API и фиксы. Нет разделения на бесплатную/платную версии — инструмент полностью бесплатный и открытый.

### Основные инструменты

theHarvester — CLI-утилита на Python с богатым набором опций:

- **Источники данных** (-b SOURCE): Более 40 источников, включая baidu, bing, brave, bufferoverun, censys, crtsh, dnsdumpster, duckduckgo, github-code, hackertarget, hunter, intelx, netlas, otx, securityTrails, shodan, urlscan, virustotal, zoomeye и многие другие. Можно использовать "all" для всех источников.
- **Основные опции**:
    - -d DOMAIN: Целевой домен или компания.
    - -l LIMIT: Ограничение количества результатов.
    - -f FILENAME: Сохранение результатов в HTML/XML/JSON.
    - -s: Скриншоты найденных субдоменов.
    - -t: DNS brute-force для субдоменов.
    - -n: DNS reverse lookup.
    - -v: Проверка хостов через DNS.
    - --screenshot: Скриншоты сайтов.
    - Поддержка прокси, API-ключей (в файле api-keys.yaml) и виртуального окружения.

Пример использования:

text

```
theHarvester -d example.com -l 500 -b all -f results.html
```

Инструмент выводит emails, hosts, IPs, subdomains и summary.

### Ссылка для скачивания

Официальный репозиторий: **[https://github.com/laramies/theHarvester](https://github.com/laramies/theHarvester?referrer=grok.com)**

Установка (рекомендуется клонировать для свежей версии):

text

```
git clone https://github.com/laramies/theHarvester.git
cd theHarvester
pip install -r requirements.txt  # Или uv sync для виртуального окружения
```

В Kali Linux: sudo apt install theharvester (но может быть не самая свежая версия). После установки запускайте theHarvester. Для API-ключей смотрите wiki репозитория.



## **Google Dorks**
### Описание

**Google Dorks** (или **Google Hacking**) — это техника использования продвинутых операторов поиска Google для нахождения скрытой, чувствительной или уязвимой информации в индексе поисковика. Dorks позволяют искать конкретные файлы, уязвимости, логины, конфиги, открытые директории, камеры и многое другое, что не видно в обычном поиске. Техника популярна в **OSINT** (Open Source Intelligence), пентестинге, bug bounty и кибербезопасности. Основная база — **Google Hacking Database (GHDB)** на Exploit-DB, где собраны тысячи готовых dorks. Используйте только в этичных целях (на своих сайтах или с разрешением)!

### Версии Google Dorks (на начало 2026 года)

Google Dorks — это не программа с версиями, а набор поисковых запросов и операторов, которые эволюционируют с изменениями в Google Search. Основная база **GHDB** (Google Hacking Database) поддерживается сообществом на **Exploit-DB** (Offensive Security) и содержит **более 7800 dorks** (по состоянию на 2025–2026 годы, с регулярными обновлениями). Нет "релизов" как у софта, но база обновляется ежемесячно/ежеквартально новыми dorks от сообщества. Актуальная версия GHDB доступна онлайн и в дампах (JSON/CSV).

### Основные инструменты

Google Dorks — это ручная техника (просто вводите в поиск Google), но есть автоматизирующие инструменты:

- **Pagodo** — Автоматически скачивает dorks из GHDB и ищет по ним (Python, с GUI).
- **GoogleDorks Toolkit** — Автоматизация поиска уязвимостей по домену, обход CAPTCHA.
- **GooFuzz** — Fuzzing с dorks для enumeration директорий/параметров.
- **Pentest-Tools.com Google Hacking** — Онлайн-сканер с готовыми dorks.
- **Maltego** или **theHarvester** — Интеграция dorks в OSINT-фреймворки.
- Cheat sheets: Популярные списки операторов (inurl:, filetype:, site:, intitle:, cache: и т.д.) для ручного использования.

Примеры операторов: site:example.com filetype:pdf, inurl:admin login, intitle:"index of" password.

### Ссылка для скачивания

Основная база **GHDB** не требует скачивания — используйте онлайн: **[https://www.exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database?referrer=grok.com)**

Для оффлайн-дампа или инструментов:

- Pagodo: [https://github.com/opsdisk/pagodo](https://github.com/opsdisk/pagodo?referrer=grok.com)
- Полные списки dorks (cheat sheets): [https://www.exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database?referrer=grok.com) (экспорт в CSV/JSON возможен через инструменты вроде ghdb_scraper).

Для практики — только этично!
