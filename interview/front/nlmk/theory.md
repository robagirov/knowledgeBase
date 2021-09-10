# Junior
## Basics
### Http
HyperText Transfer Protocol - протокол передачи гипертекста. Сейчас явл. протоколом клиент-серверного взаимодействия, что означает инициирование запросов самим получателем, кот. обычно явл. веб-браузер. На данный момент лежит в основе обмена данными в интернете.
### Чем отличается http от https?
Главное отличие в отсутствии и наличии шифрования передаваемых данных.
### Что такое webpack, gulp?
Webpack это мощный многофункциональный бандлер, предназначенный для удобства в разработке и сборке js приложений и spa.  
A Gulp всего лишь такс-раннер, упрощающий работу с рутинными задачами.
### Что такое спецификация?
Это часть документации, кот. описывает ЯП, для согласования поведения ЯП между разработчиками языка и его пользователями. Несколько форм:
- описание синтаксиса и семантики языка
- описание компилятора

## HTML
### Теги
Основа языка HTML. Используется для разграничения элементов в разметке. Они строятся в дерево html элементов и текстовых узлов. М.б. 5 видов:
- одиночные или пустые - `br, meta, input`
- с неформатированным сореджимым - `script, style`
- выводящие неформат. текст - `textarea, title`
- все остальные
### Атрибуты
Добавляются к тегам и могут изменять отображение или поведение тегов в браузере. Могут быть как глобальными, кот. можно применять к любым тегам, так и "локальные" применимые только к определенным тегам.

## Git
### Что такое система контроля версий?
Это система позволяющая отслеживать изменения в одном или нескольких файлах.
### Что такое HEAD?
Это указатель который ссылается на определенный коммит в репозитории. Или:
1. Это указатель на коммит, кот. станет родителем для след. коммита.
2. Указывает на коммит, относительно которого будет создана рабочая копия новой ветки.

### Что такое репозиторий?
Это хранилище файлов, в котором была произведена инициализация GIT и заданы базовые настройки работы с ним. Также она ограничивает диапазон файловой системы в рамках кот. будет производится контроль версий.
### Что такое коммит?
Это команда для записи индексированных изменений.
### Что такое ветка?
Это просто перемещаемый указатель для коммитов.
### Состояния файлов
1. modified - измененные, модифицированные
2. staged - индексированные, модифицированные файлы, при этом помеченные, как готовые для фиксации
3. commited - изменения в файлах зафиксированы

### Команды
* `init` - в текущем каталоге, создается подкаталог `.git` содержащий структуру гит репозитория
* `commit` - фиксирует изменения в файлах добавленных в индекс
* `clone` - копирует существующий git репозиторий
* `status` - отображает информацию по состоянию файлов
* `diff` - отображает разницу между любыми двумя git деревьями
* `branch` - без параметров, выводит список веток
    * `v` - последний коммит на каждой из веток
    * `m` - переименовать текущую ветку
* `checkout` - позволяет перемещаться между созданными ветками
* `pull` - позволяет получить все изменения из указанной ветки, чаще всего удаленного репозитория. По сути шорткод для команд `fetch` и `merge`
* `push` - отправляет все закоммиченные изменения в указанную ветку, -//-
* `merge` - выполняет слияние отдельных веток в одну
* `log` - выводит информацию об истории коммитов
* `fetch` - получает все изменения с сервера, но не сливает их в локальную копию, для этого нужно воспользоваться командой `merge`

## JS
### Синтаксис и базовые структуры
В javascript перевод строки почти всегда подразумевает точку с запятой. Точка с запятой завершает блок выполнения кода.  
Блоки кода задаются фигурными скобками, кот. сами по себе не создают отдельную область видимости.
Комментарии игнорируются интерпертатором.
### Манипуляции с DOM
DOM - document object model или объектная модель документа, это древовидная представление содержимого веб страницы. Также возможен таргетинг узлов с помощью селекторов. Можно также комбинировать CSS селекторы и реляционные свойства.  
Каждый DOM узел является объектом с множеством свойств и методов. Это основные инструменты для взаимодействия JS с DOM узлами. Можно делать:
- запросы селекторов
- удалять, добавлять, создавать и изменять элементы
- добавлять и изменять инлайн стили
- -//- атрибуты
- работать с классами
- добавлять текст и html
### Что такое ECMAScript?
Это стандарт (формально описывающий синтаксис и работу яп) языка программирования javascript. По ECMAScript есть спецификация, кот. подробно описывает синтаксис, управляющие конструкции и базовые объекты языка.
### Основы
#### Типы данных
* `number` - для любых чисел: целочисленных или чисел с плавающей точкой. Ограничены диапазоном.
* `bigint` - для целых чисел произвольной длины
* `string` - для строк. Может содержать ноль или больше символов. Нет отдельного символьного типа.
* `boolean` - для `true` / `false`
* `null` - для неизвестных значений, отдельный тип, имеющий одно значение `null`
* `undefined` - для неприсвоенных значений, -//- `undefined`
* `object` - для структур данных
* `symbol` - для уникальных идентификаторов

#### Event Bubbling - Всплытие и погружение
Принцип всплытия состоит в том, что когда событие происходит, обработчики сначала срабатывают на нём, потом на его родителе и так вверх по цепочке предков. Большинство событий подвержено всплытию, но не все.  
Самый глубокий элемент, кот. вызывает событие наз-ся целевым элементов и доступен через `event.target`. В отличии от него `this` (=`event.currentTarget`) показывает "текущий" элемент до кот. дошло всплытие.  
По умолчанию вспылтие дойдет и до `hmtl` и `document` и иногда даже до `window`. Чтобы остановить всплытие можно использовать метод `event.stopPropagation()`.  
Еще одна фаза цикла события "погружение". 3 фазы прохода события:
1. Погружение (capturing phase) – событие идёт вниз
2. Цель (target phase) – событие достигло целевого(исходного) элемента
3. Всплытие (bubbling stage) – событие начинает всплывать

#### Scope
Область видимости или Scope, определяет видимость или доступность переменной или другого ресурса в области видимости кода.
* глобальная область видимости или Global Scope - в js одна. Область за пределами всех функций считается глобальной и переменные опр. в глоб. обл. м.б. доступны и изменены в любых других областях.
* Локальная область видимости или Local Scope - каждая функция имеет свою область видимости. Переменные объявленые внутри функции становятся локальными и рассм. в соотв. локальной области. Одна и та же переменная может использоваться в разных функциях, поскольку они не являются взаимовидимыми.
   * Область видимости функции - переменная объявленная внутри функции видна только внутри неё и не может быть доступна вне её.
   * Область видимости блока - область видимости определяется фигурными скобками. Ключевые слова `const` и `let` позволяют объявлять переменные внутри области видимости блока, т.е. они существуют только внутри блока.
* Лексическая область видимости - означает, что дочерняя область имеет доступ к переменным, определенным в родительской области. Лексически связаны с контекстом исполнения их родителей. Иначе говоря, это набор правил о том как и где движок js может найти переменную. Ключевой хар-кой явл. то что, контекст определяется в момент написания кода.
* Динамическая область видимости - подразумевает модель, при кот. область видимости определяется во время выполнения, а не статически во время создания. Она не связана с тем, как и где объявляются функции, а с тем откуда они вызываются.

#### Прототипное наследование
Это возможность языка позволяющая наследовать свойства родительского объекта при создании нового. В JS объекты имеют скрытое свойств `[[Prototype]]`, оно либо равно `null` либо ссылается на другой объект. При попытке обратить к отсутствующему свойству объекта, js авто. берет его из прототипа. Методы в объектах всегда раб. с текущим объектом даже если они наследуются. Цикл `for ... in` перебирает и свои и унаследованные свойства.

#### Event loop
1. Heap (куча) - объекты собраны в кучу, наименее структурированная часть памяти.
2. Stack (стек) - единственный поток выполнения.
3. Browser or Web API’s (браузерные или веб API) - встроены в браузер. Не явл. частью языка JS, но построены на его основе.

#### This
В методах объекта используется для доступа к информации внутри объекта. This не явл. фиксированным, может использоваться в любой функции. Оно вычисляется во время выполнения и зависит от контекста.

#### Каррирование
Это расложение функции из множества аргументов на несколько функций с одним аргументом. Разбиение зависит от кол-ва аргументов (арности). Каррирование не вызывает функцию, а только преобразует её.

#### Cобытия
Это сигнал от браузера о том, что что-то произошло. Все DOM узлы подают такие сигналы. Список самых частых:
- события мыши
- события на элементах управления
- клавиатурные события
- события документа
- CSS events

Событию можно назначить обработчик, т.е. функцию кот. будет выполнена, когда событие произойдет. Несколько способов назначения такого обработчика:
- использование атрибута html тега
- Использование свойства DOM-объекта `elem.onclick` - таким способом можно назначить только 1 обработчик

> Обработчик всегда хранится в свойстве DOM-объекта, а атрибут – лишь один из способов его инициализации.

Внутри обработчика `this` ссылается на текущий элемент, т.е. на тот на кот. висит обработчик.
- addEventListener

Когда происходит событие, браузер создает объект события, записывает в него детали события и передает его в качестве аргумента функции-обработчику.