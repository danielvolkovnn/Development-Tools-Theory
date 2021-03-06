# Билет №9
## Текстовые редакторы. Возможности, сравнительный анализ популярных редакторов

__Текстовый редактор__ — самостоятельная компьютерная программа или компонент программного комплекса (например, редактор исходного кода интегрированной среды разработки или окно ввода в браузере), предназначенная для создания и изменения текстовых данных в общем и текстовых файлов в частности.

## Важные свойства редакторов

* Кросс-платформенность
* Настраиваемость
    * Шрифты, оформление, клавиатурные комбинации
* Расширяемость
    * Новые языки программирования и форматы файлов
* Программируемость
    * Программируемость сложных операций (макросы, сценарии)
* Скорость работы

## Типичные операции

* Навигация
    * По файлам
    * Перебор закладок
    * Боковая панель
    * Go to anything
    * Внутри файлов
        * Хождение по словам, строкам, экрану
        * Переход на строку
        * Переход между скобками
        * Go to symbol
* Выделение
    * Слов, Строк
    * Абзацев
    * Выражений внутри скобок
    * Всех вхождений слова => Поиск
* Поиск (и замена)
    * Простой поиск
        * Multiple cursor
        * Регулярные выражения
    * Инкрементальный
    * Быстрый
* Редактирование
    * Комментирование
    * Перестановка двух символов
    * Удаление: слов, строк, окончаний строк
    * Манипуляции со строками
        * Дублирование, переупорядочение, сортировка
        * Слияние и автоматический перенос
    * Редактирование нескольких строк и прямоугольных регионов

## Сравнительный анализ

### Atom

* Бесплатный
* Обширное количество packages(плагинов) для добавления дополнительного функционала
* Возможность кастомизации
* Подтормаживает при смене файлов или переключении вкладок

### Sublime

* Платный (но есть бесплатная версия)
* Большое количество packages, как в Atom
* Возможность кастомизации такие же как в Atom
* Гораздо шустрее Atom

### Visual Studio Code

* Бесплатный
* Много плагинов
* Встроенный Git
* Ничем не уступает в кастомизации
* Несмотря на то, что VS Code, как и Atom, созданы на базе Node.js, Electron, HTML, and CSS, VS Code достаточно быстр, в отличии от Atom

### Vim

* Бесплатный
* Более 14 000 packages – на все случаи жизни.
* Текстовый редактор в командной строке – может быть тяжел в освоении.
* Скорость работы, по большому счету, зависит от пользователя. Для быстрой работы нужно изучение большого количества горячих клавиш.
* Отлично кастомизируется.

### Emacs
* "Всё в одном"
    * Функциональность: базовая, основной режим, дополнительные режимы
* Расширяемость
    * Программируется на Elisp, имеются пакеты расширений,клавиатурные комбинации
* Настраиваемость под пользователя
    * Elisp-переменные, определение функций, создание hook'ов
* Документированность
    * Подробная документация, вплоть до функций и переменных
* Труден в освоении


## Инструменты отладки. Отладочная информация, терминология, популярные команды GDB.

**Отладка** - это процесс нахождения и устранения ошибок и дефектов в
    компьютерной программе или в электронном оборудовании.

**Отладчик** - это компьютерная программа, которая используется для
    тестирования и отладки других программ.

## Инструменты отладки

* **GDB**: GNU отладчик
* **Valgrind**: утилита для отладки проблем с памятью, утечек памяти и
    профилирования
* **strace**: трассирование системных вызовов
* **OProfile**: профилировщик для Linux систем

## Отладочная информация

* Информация, которую компилятор языка программирования генерирует автоматически на основе исходных кодов
* Специфичный кусок машинного кода, описывающий текущий исполняемый модуль
* Отладочная информация может компилироваться вместе с бинарным исполняемым файлом, и входить в его состав, может присутствовать в качестве отдельного файла, либо же просто отбрасываться на этапе компиляции и/или линковки
* Позволяет человеку использовать отладочные данные о двоичном файле, такие как имена переменных, процедур и функций из исходного кода
* Информация может быть крайне полезной во время поиска ошибок в исходном коде, отладке программы и разного рода отказах

* Содержит лог выполнения программы
* Позволяет выявить потенциально некорректные строки кода
* Указывает конкретные файл и строку в нем при некорректной работе программы

## Терминология

### Breakpoint

__Breakpoint__ (точка останова) - это преднамеренное прерывание выполнения программы, при котором выполняется вызов отладчика.

Типы точек останова:

* Точка останова с поддержкой аппаратуры
* Точка останова реализованная программно

Примеры команд для GDB: break, rbreak, tbreak

### Watchpoint

__Watchpoint__ - точка останова по данным. Срабатывает, когда меняется значение заданного выражения или переменной.

Примеры команд для GDB: watch, rwatch, awatch

### Checkpoint

__Checkpoint__ - снимок состояния программы.

Плюсы:

* Возможность начать отладку с определенной точки
* Иногда можно откатить операции ввода/вывода
* Можно обойти проблемы с рандомизацией адресного пространства в системах GNU Linux

Минусы:

* Не подходит для многопоточной программы
* Меняется идентификатор отлаживаемого процесса
* Действия с вводом/выводом нельзя отменить полностью

### Catchpoint

__Catchpoint__ - специальная точка останова, которая срабатывает при достижении специального события, например, C++ исключения или загрузки библиотеки.

Примеры команд для GDB: catch throw, catch catch, catch syscall, catch load.

### Call stack

__Call stack__ (стек вызовов) - хранит информацию об активных процедурах и функциях.

## Популярные команды GDB

* **`$ gdb --args <программа с аргументами>`**
* **`r, run [аргументы]`** - запуск программы под GDB
* **`start [аргументы]`** - удобный способ запуска программы с точкой останова на первой строчке функции `main`
* **`attach <pid> / detach`** - отладка уже запущенного процесса
* **`continue, c, fg`** - возобновление исполнения программы
* **`s, step [count]`** - продолжить исполнение до следующей строчки исходного кода
* **`n, next [count]`** - продолжить исполнение до следующей строчки исходного кода в текущем фрейме
* **`bt, backtrace [full] [n]`** - напечатать стек вызовов
* **`info args`** - вывести аргументы для текущего фрейма
* **`info locals`** - вывести локальные переменные для текущего 
