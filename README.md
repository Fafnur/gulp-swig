Gulp & Swig
========================

Gulp & Swig - сконфигурированный gulpfile.js с включенными модулями,
такиеми как gulp-swig. Данная конфигурация, направленна на упрощение
интеграции с шаблонизатором Twig, используемый по умолчанию в Symfony,
т.к. Swig максимально приближен к Twig.

Сборка была создана под влиянием проекта  https://github.com/tars/tars
из которого был оставлен минимальный, но достаточный  для верстки функционал,
для создания полномасштабных приложений.

Что включено?
--------------

В данной конфигации включены следующие пакеты:

  * gulp;
  
  * browser-sync;
  
  * gulp-swig;
  
  * chokidar;
  
  * gulp-less;
  
  * gulp-rename;
  
  * gulp-minify-css;
  
  * gulp-autoprefixer;
  
  * path;
  
  * gulp-notify;

Из списка видно, что включен browser-sync, который запускает сервер
на по адресу localhost:3000 и реализует livereload.

Сhokidar продвинутый watcher который позволяет добавлять и отслеживать файлы 
добавленные посде запуска сервера.
 
Так же поумолчанию включен и подключен Twitter Bootstrap с jQuery v1.11.3.


Как установить и запустить?
--------------
Установка стандартная, как для любой сборки на nodeJs:

```shell
npm install
```

Для запуска используется команда:

```shell
gulp 
```

т.е. запускается задача по умолчанию (gulp default).

Как работает?
--------------

После запуска создаются все задачи и наблюдатели.

Так же создается папка web/dev/, в которую копируются все статические файлы 
из папок /markup/css,   /markup/images, /markup/fonts,  /markup/video и /markup/libs.   
 
Шаблоны swig храняться в папке /markup/pages, где base.twig - это базовый шаблон для всех страниц.
Стоит заметить расширение у файлов шаблонов не имеет значения,можно называть их и '.swig',
но для упрощения интеграции с Twig, используются расширения '.twig';
