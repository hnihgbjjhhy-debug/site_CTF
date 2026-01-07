## **Frida**
### Описание

**Frida** — это динамический инструмент для инструментализации и отладки приложений (dynamic instrumentation toolkit). Он позволяет внедрять JavaScript/Python-код в запущенные процессы на Windows, macOS, Linux, iOS, Android и QNX в реальном времени без необходимости исходного кода или перекомпиляции приложения. Frida — один из самых мощных инструментов для реверс-инжиниринга мобильных приложений, обхода защит (root/jailbreak detection, SSL pinning), анализа malware, автоматизации тестирования и CTF-задач категории Mobile/Reverse. Frida работает на базе инжекта кода через ptrace (Linux/Android), Mach APIs (iOS/macOS) или Windows API.

### Версии Frida (на начало 2026 года)

На январь 2026 года актуальная стабильная версия — **Frida 16.4.x** (последний релиз 16.4.2 от декабря 2025). Frida-core и клиентские библиотеки (frida-tools, frida-gum и т.д.) обновляются синхронно. Поддерживаются:

- Python 3.8–3.13
- Node.js 18+
- Android 5.0–16
- iOS 11–18 (включая iOS 18+ с частичными ограничениями из-за новых защит Apple)

### Основные инструменты

- **frida** — CLI для работы с устройствами и процессами (frida-ps, frida-trace, frida-discover).
- **frida-trace** — автоматическая генерация трассировочных скриптов по функциям/модулям.
- **frida-ls-devices / frida-ps** — список устройств и процессов.
- **frida-repl** — интерактивная консоль JavaScript/Python.
- **frida-server** — серверная часть, которая ставится на мобильное устройство (Android/iOS).
- **frida-tools** — набор утилит (pip-пакет): frida, frida-trace, frida-kill и т.д.
- **frida-gadget** — библиотека для встраивания Frida в APK/IPA без root (обход SSL pinning в продакшен-приложениях).
- **Обфускация и стелс** — модули frida-anti-detection, frida-ios-hook и т.д.

Пример простого хука:

JavaScript

```
Java.perform(() => {
    const Activity = Java.use("android.app.Activity");
    Activity.onResume.implementation = function () {
        console.log("[*] onResume called!");
        this.onResume();
    };
});
```

### Ссылка для скачивания

Официальный сайт и релизы: **[https://frida.re](https://frida.re/?referrer=grok.com)**

- Прямая ссылка на последние релизы: [https://github.com/frida/frida/releases](https://github.com/frida/frida/releases?referrer=grok.com) (скачивайте frida-server для устройств, frida-tools для ПК)

Установка на ПК (рекомендуется):

Bash

```
pip install frida-tools   # для работы с ПК
# или
npm install -g frida      # через Node.js
```

Для Android/iOS: скачайте соответствующий frida-server с [https://github.com/frida/frida/releases](https://github.com/frida/frida/releases?referrer=grok.com) и запустите на устройстве.

Frida — must-have инструмент для любого мобильного реверсера!



## **MobSF**
### Описание

**MobSF** (Mobile Security Framework) — это открытый автоматизированный фреймворк для пентестирования, анализа вредоносного ПО и оценки безопасности мобильных приложений на платформах **Android**, **iOS** и **Windows**. Он поддерживает **статический** (анализ кода без запуска) и **динамический** (анализ во время выполнения) анализ, а также тестирование Web API. MobSF популярен в CTF (категория Mobile), среди пентестеров и разработчиков для быстрого обнаружения уязвимостей, таких как небезопасное хранение данных, слабая криптография, утечки и т.д. Фреймворк имеет веб-интерфейс, REST API для интеграции в CI/CD и CLI-инструменты.

### Версии MobSF (на начало 2026 года)

На январь 2026 года последняя стабильная версия — **v4.4.2** (с hotfix'ами и улучшениями, такими как поддержка Docker для динамического анализа Android, улучшения SAST и исправления безопасности). Проект активно развивается на GitHub, обновления выходят регулярно (включая hotfix'ы для UI и динамического анализатора). Нет разделения на бесплатную/платную версии — полностью open-source.

### Основные инструменты

MobSF предоставляет веб-интерфейс и набор модулей:

- **Static Analysis**: Декомпиляция APK/IPA, анализ манифеста, поиск hardcoded secrets, уязвимостей (по OWASP MSTG/MASVS), извлечение строк, разрешений, сертификатов.
- **Dynamic Analysis**: Запуск приложения в эмуляторе/реальном устройстве (Android/iOS), перехват трафика (HTTP/HTTPS), логирование runtime, инъекция хуков (Frida-based), анализ файловой системы.
- **Malware Analysis**: Проверка на вредоносные домены, сигнатуры, permissions abuse.
- **API Testing**: Фаззинг Web API (с CapFuzz).
- **Дополнительно**: Генерация отчётов (PDF/HTML), mobsfscan (отдельный инструмент для статического анализа исходного кода на Java/Kotlin/Swift), интеграция с DevSecOps, поддержка Docker.

Пример использования: Загрузите APK/IPA в веб-интерфейс (localhost:8000) → получите полный отчёт с рисками.

### Ссылка для скачивания

Официальный репозиторий: **[https://github.com/MobSF/Mobile-Security-Framework-MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF?referrer=grok.com)**

Установка (рекомендуется клонирование):


```
git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
cd Mobile-Security-Framework-MobSF
./setup.sh  # Для Linux/macOS (или setup.bat для Windows)
./run.sh  # Запуск
```

Или через Docker:


```
docker pull opensecurity/mobile-security-framework-mobsf:latest
docker run -it -p 8000:8000 opensecurity/mobile-security-framework-mobsf:latest
```

Документация: [https://mobsf.github.io/docs/](https://mobsf.github.io/docs/?referrer=grok.com)



## **Jadx**
### Описание

**Jadx** — это открытый декомпилятор (decompiler) и дизассемблер для Android-приложений. Он преобразует Dalvik-байткод (DEX) из APK, AAB, DEX, JAR, CLASS, ZIP и других файлов в читаемый Java-код. Jadx включает два основных компонента: командную строку (jadx-cli) и графический интерфейс (jadx-gui). Инструмент популярен в реверс-инжиниринге мобильных приложений, CTF (категория Mobile), анализе malware и bug bounty. Jadx декомпилирует код, декодирует ресурсы (AndroidManifest.xml, XML, изображения), поддерживает деобфускацию и экспорт в Gradle-проект. Он не всегда даёт 100% точный код (из-за оптимизаций и обфускации), но часто лучше аналогов вроде APKTool + dex2jar.

### Версии Jadx (на начало 2026 года)

Проект активно развивается на GitHub (skylot/jadx). Последняя стабильная версия — **1.5.3** (выпущена в конце 2025 года). Основные улучшения в недавних релизах: поддержка AAB-парсинга, поиск в ресурсах, редактирование smali, экспорт с compileSdkVersion, поддержка новых DEX-форматов и плагины. Обновления выходят регулярно, часто с фиксами для GUI и core.

### Основные инструменты

- **jadx-cli** (командная строка): Декомпиляция с опциями (--no-res, --deobf, --export-gradle, --threads-count и т.д.).
- **jadx-gui**: Графический интерфейс с деревом классов, поиском, навигацией по коду, редактированием комментариев/имен, просмотром ресурсов (XML, изображения), смали-режимом и деобфускацией.
- **Deobfuscator**: Автоматическое переименование обфусцированных имён.
- **Плагины**: Система плагинов (установка через jadx plugins --install).
- **Дополнительно**: Экспорт в Gradle, поиск по коду/ресурсам, поддержка отладки (debugger).

Пример использования: jadx-gui app.apk — открыть APK в GUI.

### Ссылка для скачивания

Официальный репозиторий и релизы: **[https://github.com/skylot/jadx/releases](https://github.com/skylot/jadx/releases?referrer=grok.com)**

Скачайте последнюю версию (jadx-*.zip или платформо-специфичные билды). Для CLI/GUI без установки JRE — кросс-платформенный zip. Требуется Java 11+ (64-bit). В Kali Linux: часто предустановлен или через пакетный менеджер.