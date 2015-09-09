[![Build Status][travis-badge]][travis-link]
[![GitHub release][release-badge]][release-link]

Скрипт **Setup-openwith** для электронных книг PocketBook с прошивкой 5.x, настраивающий **Дополнительное меню настроек "Открыть с помощью"**
==================================================
**Новое меню дополнительных настроек появится в настройках "Персонализация" -> "Открыть с помощью".**

Интерфейс скрипта Setup-openwith и настроенного нового меню являются мультиязычными, насколько позволяет имеющаяся локализация PocketBook.
Скрипт создавался независимым от модели и прошивки PocketBook, но отлаживался только на PocketBook 650.

Описание настроечного скрипта Setup-openwith
---------------------------------------------
- Установка скрипта производится копированием файла Setup-openwith.app в папку /applications/ во внутренней памяти устройства.
- Скрипт добавляет в меню настроек возможность настроить приложение "по умолчанию" которым будет открываться файл с указанным расширением.
- В меню добавляются только те расширения файлов и программы, которые на момент запуска скрипта Setup-openwith были прописаны в файлах extensions.cfg внутри прошивки и во внутренней памяти, а так же были настроены на открытие разными программами.
- По окончанию настройки скрипт предложит сам себя удалить (рекомендую его оставить хотя бы на случай обновления прошивки).

>**ВАЖНО! После обновления прошивки обязательно перезапустите скрипт Setup-openwith для обновления нового меню настроек, иначе меню настроек Персонализация останется от старой прошивки и будет не корректно работать.
Для перенастройки дополнительного меню "Открыть с помощью" достаточно просто запустить заново скрипт Setup-openwith (без удаления через меню).**

Описание дополнительных настроек "Открыть с помощью"
-----------------------------------------------------
- Пункт меню "Применение настроек" - вносит настроенные изменения в файл extensions.cfg (находящийся во внутренней памяти устройства), указывая программу по умолчанию только в тех местах строк где надо не добавляя и не удаляя строк. (Если программа для открытия необходимого файла уже указана, то она перемещается на первое место, если ее нет, то программа добавляется).
- Пункт меню "Очистить историю" - удаляет файл handlers.cfg из внутренней памяти, что позволяет сбросить соответствие какой штатной программой открывалась (и будет далее открываться по умолчанию) последний раз книга.
- Пункт меню "Удалить" полностью удаляет дополнительное меню "Открыть с помощью". При этом extensions.cfg остается с последними примененными ранее настройками.

После настройки скрипт создает во внутренней памяти следующие файлы:
```
/mnt/ext1/system/bin/openwith_apply.app
/mnt/ext1/system/bin/openwith_clear.app
/mnt/ext1/system/bin/openwith_remove.app
/mnt/ext1/system/config/openwith.cfg
/mnt/ext1/system/config/settings/personalize.json
/mnt/ext1/system/config/settings/openwith.json
```
Для ручного удаления дополнительного меню "Открыть с помощью", достаточно удаления этих файлов.

[travis-badge]:https://travis-ci.org/Lighting/Setup-openwith.svg?branch=master
[travis-link]:https://travis-ci.org/Lighting/Setup-openwith
[release-badge]:https://badge.fury.io/gh/lighting%2FSetup-openwith.svg
[release-link]:https://github.com/Lighting/Setup-openwith/releases/latest
