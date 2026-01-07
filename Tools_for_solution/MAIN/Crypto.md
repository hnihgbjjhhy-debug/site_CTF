
## **CyberChef**
### Описание

**CyberChef** — это бесплатный, open-source веб-инструмент (так называемый «Cyber Swiss Army Knife»), разработанный **GCHQ** (Government Communications Headquarters, Великобритания). Он предназначен для анализа, декодирования, шифрования, сжатия и преобразования данных прямо в браузере.

CyberChef работает **полностью на стороне клиента** (в вашем браузере), без отправки данных на сервер — это делает его безопасным для работы с чувствительной информацией. Нет установки, просто открываете страницу и начинаете использовать.

Основная идея: перетаскиваете операции (operations) в «рецепт» (recipe), и CyberChef автоматически применяет их к входным данным («bake» происходит мгновенно). Подходит для:

- CTF-задач
- Форензики
- Анализа malware
- Декодирования base64 / hex / URL / JWT
- Работы с криптографией
- Парсинга форматов (JSON, ASN.1, X.509 и т.д.)

### Версии CyberChef (на начало 2026 года)

CyberChef использует семантическое версионирование (semver). На январь 2026 года актуальная версия — **v10.19.4** (последний релиз от октября 2025 года).

Проект активно развивается, но major-версия остаётся 10.x уже несколько лет (с 2020-х). Обновления выходят регулярно (bug fixes, новые операции, улучшения интерфейса).

- Последний релиз: v10.19.4 (23 октября 2025)
- Официально: всё ещё «under active development», но стабильный и очень зрелый инструмент.
- Онлайн-версия всегда самая свежая, standalone-версия (ZIP) — фиксированная на момент скачивания.

### Основные инструменты

CyberChef состоит из четырёх основных панелей и огромного списка операций (более 400+):

- **Input** — область ввода данных (текст, файл до ~2 ГБ)
- **Output** — результат после применения рецепта
- **Recipe** — цепочка операций (drag-and-drop), можно сохранять, импортировать/экспортировать
- **Operations** — левая панель со всеми функциями (поиск, категории: Crypto, Data Format, Compression, Hashing, Binary и т.д.)

Популярные категории и примеры операций:

- **Encoding/Decoding** — From/To Base64, Hex, URL, Binary, ASCII85, Base58, JWT Decode
- **Crypto** — AES, DES, RSA, Blowfish, RC4, XOR, Vigenère, ChaCha, Hash (MD5, SHA, bcrypt и т.д.)
- **Compression** — Gzip, Zlib, Brotli, ZIP, TAR
- **Data Analysis** — Magic (авто-определение), Extract Files, Find / Replace, Regular Expression
- **Binary / File** — From Hexdump, Parse X.509, ASN.1 decoder, PDF Analyse
- **Networking** — HTTP request, DNS over HTTPS, IP geolocation
- **Utils** — Delay, Fork, Merge, Substring, Reverse, Rotate, Whitespace

Особенности:

- Автоматический «Magic» — пытается угадать, что делать с данными
- Поддержка drag-and-drop файлов
- Сохранение рецептов в URL (можно делиться ссылкой)
- Темы (тёмная/светлая), поиск операций, контекстная помощь (F1)

### Ссылка для скачивания

Официальная онлайн-версия (всегда актуальная): **[https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/?referrer=grok.com)**

Для оффлайн-использования (standalone ZIP, не обновляется автоматически): Скачать с GitHub Releases → [https://github.com/gchq/CyberChef/releases](https://github.com/gchq/CyberChef/releases?referrer=grok.com) (Выберите последнюю версию → Assets → CyberChef_v10.19.4.zip или новее)

Репозиторий проекта: [https://github.com/gchq/CyberChef](https://github.com/gchq/CyberChef?referrer=grok.com)



## **SageMath**

### Описание

**SageMath** (ранее известен как Sage) — это бесплатная, open-source система компьютерной алгебры (CAS) и математическое программное обеспечение. Оно создано как альтернатива коммерческим системам вроде Mathematica, Maple, MATLAB и Magma. SageMath построено на Python (с использованием Cython) и объединяет сотни open-source библиотек в единую платформу.

Основные области применения: алгебра, комбинаторика, теория чисел, криптография, графы, геометрия, численный анализ, статистика, дифференциальные уравнения и многое другое. Интерфейс — Jupyter Notebook, командная строка или веб-сервер. SageMath идеален для образования, исследований и вычислений, где нужна интеграция разных инструментов без "переизобретения колеса".

### Версии SageMath (на начало 2026 года)

На январь 2026 года последняя стабильная версия — **10.8** (декабрь 2025 года, с release candidates в декабре 2025). Разработка продолжается активно на GitHub, обновления выходят регулярно. Предыдущие значимые: 10.0 (май 2023). Проект использует семантическое версионирование, но major-версия остаётся 10.x уже несколько лет. Нет платных версий — полностью бесплатный и open-source под GPL.

### Основные инструменты

SageMath интегрирует множество пакетов, предоставляя единый Python-подобный интерфейс:

- **Символьные вычисления**: SymPy, Maxima (для алгебры, интегралов, дифференцирования).
- **Численные расчёты**: NumPy, SciPy, GSL.
- **Графика и визуализация**: Matplotlib, 2D/3D-плоты, интерактивные графики.
- **Теория чисел и криптография**: PARI/GP, FLINT.
- **Группы, комбинаторика, графы**: GAP, NetworkX.
- **Статистика**: R (через rpy2).
- **Другие**: Singular (коммутативная алгебра), Octave/MATLAB-подобные функции.

Дополнительно:

- Jupyter Notebook с поддержкой LaTeX, 3D (Jmol).
- Sage Cell Server для онлайн-вычислений.
- Расширяемость: тысячи функций, написанных специально для Sage.

### Ссылка для скачивания

Официальный сайт: **[https://www.sagemath.org/](https://www.sagemath.org/?referrer=grok.com)**

- Скачивание бинарников/исходников: **[https://www.sagemath.org/download.html](https://www.sagemath.org/download.html?referrer=grok.com)** (выберите зеркало; рекомендуется через torrent для скорости).
- Исходный код (последняя стабильная): **[https://www.sagemath.org/download-source.html](https://www.sagemath.org/download-source.html?referrer=grok.com)**
- Для Linux/macOS/Windows (через Conda или WSL): инструкции в Installation Guide.
- Онлайн-версия: CoCalc[](https://cocalc.com/?referrer=grok.com) или Sage Cell[](https://sagecell.sagemath.org/?referrer=grok.com).

Для установки рекомендуется Conda: conda create -n sage sage python=3.12.



## **hashcat**

### Описание

**hashcat** — это самая быстрая и продвинутая утилита для восстановления паролей с открытым исходным кодом (open-source). Она поддерживает более **300 высокооптимизированных алгоритмов хэширования** и работает на CPU, GPU (через OpenCL/CUDA) и других ускорителях. hashcat используется в пентестинге, CTF, forensics и для аудита безопасности паролей.

Инструмент поддерживает **распределённое взлом** (distributed cracking), множество режимов атак и оптимизирован для максимальной скорости (особенно на GPU). Это эволюция старых oclHashcat (GPU) и hashcat-legacy (CPU), объединённых в один инструмент с версии 3.00. hashcat — полностью бесплатный (MIT license), активно развивается командой hashcat.

### Версии hashcat (на начало 2026 года)

На январь 2026 года последняя стабильная версия — **v7.1.2** (hotfix-релиз с исправлениями совместимости и багов в Argon2).

Значимые предыдущие:

- **v7.1.0** — добавлены новые фичи, hash-моды и bug fixes.
- **v7.0.0** — крупный рефакторинг, множество улучшений после двух лет разработки.

Обновления выходят регулярно (bug fixes, новые алгоритмы). Нет платных версий — только open-source.

### Основные инструменты

hashcat — CLI-утилита (командная строка) с огромным набором опций. Ключевые режимы атак (-a):

- **0** — Straight (dictionary attack): атака по словарю.
- **1** — Combination: комбинация слов из словарей.
- **3** — Brute-force/Mask attack: маски (?l?u?d?s и т.д.).
- **6** — Hybrid wordlist + mask.
- **7** — Hybrid mask + wordlist.
- **9** — Association attack.

Другие фичи:

- Поддержка **rules** (-r): модификация слов (например, добавление цифр, смена регистра).
- **>300 hash-модов** (-m): MD5, SHA, bcrypt, NTLM, Kerberos, Bitcoin wallets и т.д.
- Оптимизации: workload profiles, benchmark (-b), restore сессий.
- Интеграция: potfile (сохранённые пароли), outfile.
- Плагины: Python/Rust bridge для кастомных модулей.

Пример: hashcat -m 0 -a 0 hashes.txt rockyou.txt (MD5 по словарю).

### Ссылка для скачивания

Официальный репозиторий и релизы: **[https://github.com/hashcat/hashcat/releases](https://github.com/hashcat/hashcat/releases?referrer=grok.com)**

- Скачайте бинарники или исходники с последней версии.
- Официальный сайт: **[https://hashcat.net/hashcat/](https://hashcat.net/hashcat/?referrer=grok.com)** (старые версии и документация).

Для Kali Linux: sudo apt install hashcat. Для сборки из исходников — следуйте BUILD.md в репозитории.





