
## **ChipWhisperer**
### Описание

**ChipWhisperer** — это полностью открытая (open-source) инструментальная цепочка (toolchain) для исследований в области аппаратной безопасности, в частности для **side-channel power analysis** (анализ побочных каналов по энергопотреблению) и **fault injection** (внедрение сбоев, включая voltage/clock glitching). Проект разработан компанией NewAE Technology Inc. (основатель Colin O'Flynn) и предназначен для обучения, пентестирования и исследований уязвимостей встроенных устройств (микроконтроллеры, крипто-чипы и т.д.). ChipWhisperer включает аппаратные платы (capture и target), ПО на Python, firmware и FPGA-код. Он популярен в CTF (категория Hardware), академических исследованиях и среди специалистов по embedded security. Инструмент позволяет захватывать трассы энергопотребления, вводить глюки и анализировать данные для извлечения ключей (например, AES).

### Версии ChipWhisperer (на начало 2026 года)

- **Программное обеспечение**: Активно развивается. К началу 2026 года актуальные версии — **6.x** (ChipWhisperer 6.0+ с крупными изменениями в репозитории, включая очистку истории и новые фичи). Предыдущие: 5.7.x (2023–2025). Разработка на ветке develop, стабильные релизы на master.
- **Аппаратные версии** (capture-устройства):
    - **ChipWhisperer-Nano** (CW1101) — бюджетный вариант.
    - **ChipWhisperer-Lite** (CW1173) — популярный для обучения.
    - **ChipWhisperer-Pro** (CW1200) — продвинутый.
    - **ChipWhisperer-Husky** (и Husky Plus) — самая современная модель (выпущена ~2023, с улучшениями: высокоскоростной FPGA, streaming, logic analyzer). На 2026 год Husky остаётся флагманом.

### Основные инструменты

ChipWhisperer состоит из нескольких слоёв:

- **Аппаратные компоненты**:
    - Capture-платы: Захват трасс (ADC до 20–105+ MS/s), глюки (voltage/clock), триггеры.
    - Target-платы: Мишени (STM32, AVR и т.д.) с примерами кода.
    - Поддержка: SMA-коннекторы, 20-pin интерфейс, JTAG/SWD (в Husky).
- **Программные инструменты**:
    - **ChipWhisperer Capture**: Python API для управления аппаратной частью (захват трасс, глюки).
    - **ChipWhisperer Analyzer**: Python API для обработки и анализа трасс (CPA, DPA атаки).
    - Jupyter notebooks: Образовательные примеры (атаки на AES, RSA и т.д.).
    - Фичи: Синхронный захват, streaming (для длинных трасс), glitch visualization, интеграция с Jupyter.
- **Дополнительно**: Полностью открытый код (Verilog для FPGA, C для микроконтроллера), поддержка множества атак (CPA, DPA, glitch skipping checks).

### Ссылка для скачивания

Официальный репозиторий (ПО, firmware, документация): **[https://github.com/newaetech/chipwhisperer](https://github.com/newaetech/chipwhisperer?referrer=grok.com)**

- Релизы и скачивание: [https://github.com/newaetech/chipwhisperer/releases](https://github.com/newaetech/chipwhisperer/releases?referrer=grok.com)
- Установка ПО: pip install chipwhisperer (или клонировать репозиторий: git clone https://github.com/newaetech/chipwhisperer.git)
- Аппаратное обеспечение: Покупка через NewAE[](https://www.newae.com/?referrer=grok.com) или Crowd Supply (для Husky).

Документация: [https://chipwhisperer.readthedocs.io/](https://chipwhisperer.readthedocs.io/?referrer=grok.com)



## **Bus Pirate**
### Описание

**Bus Pirate** — это универсальный инструмент для аппаратного хакерства и отладки, представляющий собой недорогой USB-адаптер, который позволяет взаимодействовать с различными протоколами связи, используемыми в embedded-системах. Он может работать как I2C, SPI, UART, 1-Wire, JTAG, SWD, бит-банг (bit-bang) и многие другие протоколы. Bus Pirate часто используется для:

- чтения/записи EEPROM и flash-памяти
- отладки микроконтроллеров
- реверс-инжиниринга устройств
- работы с датчиками, дисплеями и модулями
- CTF-задач в категории Hardware
- экспериментов с аппаратными устройствами

Проект полностью open-source (аппаратная часть и ПО), изначально разработан Dangerous Prototypes (Ian Lesnet). Это один из самых популярных инструментов в сообществе hardware hackers благодаря низкой цене, простоте и широкой поддержке протоколов.

### Версии Bus Pirate (на начало 2026 года)

К началу 2026 года существуют две основные линейки:

- **Классические версии** (оригинальные Dangerous Prototypes):
    - Bus Pirate v3.6a — самая распространённая, надёжная и дешёвая модель (5 В, 3.3 В, 3.3 В/5 В совместимость).
    - Bus Pirate v4 — с улучшенным дисплеем, регулятором напряжения и USB-C.
- **Новая серия** (Dangerous Prototypes v5, 2023–2025):
    - **Bus Pirate 5** (BP5) — полностью переработанная версия с мощным микроконтроллером RP2040, поддержкой 1.2–5.5 В, встроенным OLED-дисплеем, улучшенной скоростью, режимом автономного режима и новой прошивкой.
    - **Bus Pirate 5 XL** — расширенная версия с дополнительными пинами и возможностями.

Самая актуальная версия прошивки — **5.0.x** (на базе RP2040) для BP5/BP5XL. Классические v3/v4 работают на PIC24 и имеют прошивку 7.x (последняя ~7.1).

### Основные инструменты

Bus Pirate — это многорежимный инструмент, основные режимы и функции:

- **Протоколы**:
    - I2C (до 1 МГц)
    - SPI (до 8 МГц)
    - UART (до 115200 бод, RS232/RS485)
    - 1-Wire
    - JTAG (ограниченно)
    - SWD (в новых версиях)
    - Bit-bang (ручное управление пинами)
- **Дополнительные возможности**:
    - Захват частот (frequency counter)
    - PWM-генератор
    - АЦП (аналоговый вход)
    - Программирование flash (SPI, I2C EEPROM)
    - Режим "open collector" и "open drain"
    - Встроенный регулятор 3.3 В / 5 В (до 500 мА)
    - Поддержка binmode (бинарный протокол) для интеграции с другими инструментами (например, OpenOCD, flashrom)
- **Интерфейс**:
    - Через USB (COM-порт) — работает как терминал (PuTTY, minicom, screen).
    - Графический интерфейс: Pirate Scope (Python), Bus Pirate GUI (Java).
    - Автоматический режим: BP5 имеет OLED-экран и кнопки для работы без ПК.

### Ссылка для скачивания

Официальный сайт и репозиторий: **[https://dangerousprototypes.com/docs/Bus_Pirate](https://dangerousprototypes.com/docs/Bus_Pirate?referrer=grok.com)**

- **Прошивки** (для всех версий): [https://github.com/DangerousPrototypes/Bus_Pirate5_firmware](https://github.com/DangerousPrototypes/Bus_Pirate5_firmware?referrer=grok.com) (для BP5) [https://github.com/DangerousPrototypes/Bus_Pirate](https://github.com/DangerousPrototypes/Bus_Pirate?referrer=grok.com) (для старых версий)
- **Схемы и PCB**: [https://github.com/DangerousPrototypes/Bus_Pirate5_hardware](https://github.com/DangerousPrototypes/Bus_Pirate5_hardware?referrer=grok.com)
- **Документация и wiki**: [https://buspirate.com](https://buspirate.com/?referrer=grok.com)
- **Покупка готовых устройств**: [https://dangerousprototypes.com/store/](https://dangerousprototypes.com/store/?referrer=grok.com) или Crowd Supply (для Bus Pirate 5).

Для классических версий v3/v4: Прошивка скачивается через DFU или PICkit, а для BP5 — через USB (uf2-файл).
