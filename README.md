Markup with Swig
========================

Markup & Swig - сконфигурированный gulpfile.js с включенными модулями,
такиеми как gulp-swig. Данная конфигурация, направленна на упрощение
интеграции с шаблонизатором Twig, используемый по умолчанию в Symfony,
т.к. Swig максимально приближен к Twig.
 

Что включено?
--------------
Различные модули для поддержки SwigJS и LESS. Так же есть таски для минимизации и сжатия изображений и CSS.

Для внешних записимостей используется bower.

По умолчанию включены и подключены Twitter Bootstrap с jQuery v2.1.4 с помощью Bower


Как установить и запустить?
--------------

1) Установка модулей ноды:
```shell
npm install
```

2) Установка зависимостей bower
Если bower не установлен глобально, выполнить команду
```shell
npm install -g bower
```

Установить внешние библиотеки
```shell
bower install
```

3) Установка
Если галп не установлен глобально, выполнить команду
```shell
npm install -g gulp
```

4) Запускаем Gulp.
Для запуска используется команда:
```shell
gulp 
```


Как работает?
--------------

В папке markup хранятся все шаблоны и данные (markup/data.js) для них.
В папка web, хранятся все статичные файлы.


Генерируем бем
--------------
Для запуска используется команда:

```shell
gulp bem --b name-block --e element,element2,element3 --m modify1,modify2
```

где:

--b    - название блока

--e    - название элементов

--m    - название модификаторов

--page - на какую страницу вставить html (по умолчанию markup/pages/index.twig)

--path - необязательный параметр, который позволяет добавлять блок к другим блокам( например добавить test-title.less в папку web/less/test/


Работаем с markup-templates
--------------
Реализована команда для копирования шаблонов. Для ее использования, необходимо подключить библиотеки шаблонов.
Пример библиотеки можно посмотреть в  https://github.com/fafnur/markup-templates

Вы можете использовать неограниченное количество библиотек.
Каждая библиотека должна занесена в 
```shell
src = { 
        ...
        tpl:  [
            htdocs + '/components/markup-templates/templates',
            'E:\\domains\\layouts\\templates'
        ]
        ....
    },
```
Поиск модуля в библиотеках осуществляется сверху вниз. Соответсвенно, более приоритетные библиотеки, должны быть выше.

Markup-templates по умолчанию включена в сборку.

Для копирования(клонирования) шаблона нужно выполнить следующую команду

```shell
gulp clone --from test --ver test1 --to news
```

где

--from - это название интересующего нас шаблона

--ver  - версия (подпапка в шаблоне)

--to   - имя для копируемого шаблона (заменит html и css на соответвующее имя; по умолчанию значение из --from)

--page - на какую страницу вставить html (по умолчанию markup/pages/index.html.twig)


Небольшие хаки
--------------
Для минимизации и оптимизации процесса верстки можно избежать многократной установки проекта.

Для того чтобы каждый раз не хранить node_modules для каждого из проектов, можно создать символическую ссылку.

Находясь в папке проекта нужно выполнить команду:

mklink /d "node_modules" "<путь до установленного и настроенного проекта markup-swig>"

Для windows 8 и более:

```shell
mklink /d 'node_modules' 'E:/domains/markup-swig/node_modules'
```

Стоит заметить, что это возможно использовать при условии что все проекты используют совместимые версии markup-templates:

0.1.*, 0.2.* и т.д. 