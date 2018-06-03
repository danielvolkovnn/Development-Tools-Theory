# Приведите примеры "хороших" инструментов, почему вы так считаете?


# В стабильности какого продукта вы уверены больше, для которого зарегистрировано много или мало ошибок? Почему?
# Нарисовать работу над следующим релизом

# Примеры СКВ кроме SVN и Git

## TFS - Team Foundation Server

Отображение рабочей области:

* Простота настройки и понимания
* Легко протестировать изменение библиотеки в нескольких продуктах.
* Легко получать последние изменения в библиотеке и отправлять изменения в библиотеку
* Никакой трассируемости или, по меньшей мере, меньшей проходимости, например. если в продукте A было внесено изменение в библиотеку, как отслеживать это изменение в продукте B
* Изменения в библиотеках могут влиять на продукты неконтролируемым образом.
* Сборка становится сложнее
* Каждый пользователь должен настроить свое рабочее пространство индивидуально (но в TFS 2012 Power Tools есть шаблоны рабочей области).

Отображение папок:

* Все, что необходимо, настраивается в данной ветке
* Изоляция между продуктами и отраслями.
* Сборка упрощена.
* Управление изменениями
* Требуется больше дискового пространства
* Требуется больше администрирования в виде ветвления/слияния и настройки веток.

## Mercurial (Hg)

Mercurial схожа с Git своей распределённой структурой, однако имеет более __строгий подход к ветвлению__ нежели в Git.

Это одновременно и плюс и минус
* Плюс — сложнее создать запутанную структуру в репозитории
* Минус — нет возможности перемещать правки и делать некоторые другие вещи за которые многие так любят Git

Mercurial немного хуже поддерживается разработчиками IDE, а так же имеет более скромный набор графических оболочек в отличие от Git и SVN.

## Perforce (P4)

### Плюсы

* Тотальный контроль над всем;
* Идущая от разработчиков графическая оболочка;
* Возможность удобно комбинировать работу над несколькими модулями;
* Удобная работа со списками изменений.

### Минусы

* Трудно заставить себя привыкнуть к тому, что инструмент диктует тебе как работать, а не наоборот;
* Когда теряется связь с сервером, прекращается продуктивная работа



# Укажите последовательность git команд, которые требовалось вызвать при работе над 2й и 3й лабораторными

* git checkout master
    * Переход на ветку master форкнутого репозитория
* git add remote upstream https://github.com/UNN-VMK-Software/devtools-course-practice.git
    * Добавление ссылки на главный репозиторий для получения актуальных данных
* git fetch upstream
    * Получение и сохранение на локальной машине последних изменений из upstream, т.е. с ветки master главного репозитория
* git merge upstream/master
    * Вливание полученных изменений в текущую ветку (master)
* git commit -m "some info"
    * Добавление коммита
* git push origin master
    * Фиксирование локальных изменений на удаленном репозитории
* git checkout -b lab2-YOUR-NAME
    * Создание и переход на ветку lab2-YOUR-NAME, имеющую актуальные файлы



# Почему слияние работает лучше в Git, чем в Subversion
# В чем разница между ветками в Git и Subversion
# Можно ли использовать GitHub Flow при централизованном рабочем процессе (Centralized Workflow?)
# Если задачи на ближайший релиз уже отобраны, и работа идет, как быть если находится несколько критических ошибок? Времени точно не хватит на запланированные задачи и критические ошибки.
# Что такое фреймворк модульного тестирования? Примеры для разных языков.
# Придите пример модульного, интеграционного и системного теста
# Какие инструменты из курса потребуются для реализации практики CI?
# Показать в какие моменты на ветке master запускаются билды разных подходов в эволюции CI



# Какой смысл несут слова "непрерывная" и "интеграция" в названии практики CI?

Каждое изменение __должно интегрироваться__ 
* Слово continuous в термине Continuous Integration означает «непрерывный/непрекращающийся»
    * Это означает, что в идеале сборка вашего проекта должна идти буквально все время
    * Каждое изменение в системе контроля версий должно интегрироваться без пропусков или задержек
    * Организация ночных сборок — это хорошая практика, но это не continuous integration
        * Результаты такой ночной сборки будут доступны лишь на следующий день, когда их актуальность для разработчиков уже значительно снижена
    * На практике довольно часто реализуют оба процесса и непрерывную интеграция и ночные сборки — более редкую интеграцию
    * Принцип непрерывной интеграции не выполним без другого условия — «Сборка должна идти быстро».



# Чем отличаются статические и динамические анализаторы кода. Приведите примеры ошибок, которые можно найти только одним видом инструментов, но не другим.

__ВОПРОС ГОВНО__
* Динамическое связывание может сократить общее потребление ресурсов
    * Несколько процессов должны иметь одну и ту же библиотеку одинаковой версии
    * Ресурсы включают дисковое пространство, ОЗУ и пространство кеша
    * Динамический компоновщик должен быть достаточно гибким
* исправления и обновления ошибок в библиотеках распространяются, чтобы улучшить ваш продукт, не требуя, чтобы вы отправляли что-либо

* статическое связывание означает, что вы можете знать, что код будет работать в очень ограниченных средах (в начале процесса загрузки или в режиме восстановления)

# При разговоре про преимущества автоматизации привести конкретные примеры (было-стало)
# Примеры инструментов UNIX, желательно помимо разобранных на лекциях
# В какой ситуации удобнее статическое связывание, а в какой -- динамическое?
# Почему важно не менять часто API? Если это необходимо сделать, как это делается "правильно"? (https://semver.org/lang/ru/)
# В чем достоинства и недостатки системы automake?
# Сравните форматы Markdown+Git и GoogleDocs. В каких ситуациях удобнее первый или второй вариант?
# Регулярные выражения на все случаи жизни, парсинг логов, персональных данных, извлечение информации из исходников, документации и так далее.


# Укажите последовательность git команд, которые требовалось вызвать при работе над 2й и 3й лабораторными


