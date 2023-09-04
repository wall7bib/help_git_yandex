# дыШпаргалка. Базовые команды в консоли

Чтобы вам было удобнее взаимодействовать с командной строкой, мы подготовили шпаргалку. В ней собраны все команды, о которых мы рассказали в уроках, и их полезные вариации. 

### Навигация

- `pwd` (от англ. ***p**rint **w**orking **d**irectory*, «показать рабочую папку») — покажи, в какой я папке;
- `ls` (от англ. ***l**i**s**t directory contents*, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;
- `ls -a` — покажи также скрытые файлы и папки, названия которых начинаются с символа `.`;
- `cd first-project` (от англ. ***c**hange **d**irectory*, «сменить директорию») — перейди в папку `first-project`;
- `cd first-project/html` — перейди в папку `html`, которая находится в папке `first-project`;
- `cd ..` — перейди на уровень выше, в родительскую папку;
- `cd ~` — перейди в домашнюю директорию (`/Users/Username`);
- `cd /` — перейди в корневую директорию.

### Работа с файлами и папками

**Создание**

- `touch index.html` (англ. *touch,* «коснуться») — создай файл `index.html` в текущей папке;
- `touch index.html style.css script.js` — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
- `mkdir second-project` (от англ. ***m**a**k**e **dir**ectory*, «создать директорию») — создай папку с именем `second-project` в текущей папке.

**Копирование и перемещение**

- `cp file.txt ~/my-dir` (от англ. ***c**o**p**y*, «копировать») — скопируй файл в другое место;
- `mv file.txt ~/my-dir` (от англ. ***m**o**v**e*, «переместить») — перемести файл или папку в другое место.

**Чтение**

- `cat file.txt` (от англ. *con**cat**enate and print*, «объединить и распечатать») — распечатай содержимое текстового файла `file.txt`.

**Удаление**

- `rm about.html` (от англ. ***r**e**m**ove*, «удалить») — удали файл `about.html`;
- `rmdir images` (от англ. ***r**e**m**ove **dir**ectory*, «удалить директорию») — удали папку `images`;
- `rm -r second-project` (от англ. ***r**e**m**ove,* «удалить» + ***r**ecursive*, «рекурсивный») — удали папку `second-project` и всё, что она содержит.

### Полезные возможности

- Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (`&&`).

- У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (**`↑`**) и вниз (**`↓`**).

- Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать `Tab`. Если файл или папка есть в текущей директории, командная строка допишет путь сама.

  Например, вы находитесь в папке `dev`. Начните вводить `cd first` и дважды нажмите `Tab`. Если папка `first-project` есть внутри `dev`, командная строка автоматически подставит её имя. Останется только нажать `Enter`.

💡 **Команд так много — как их запомнить?**

 Терминал — мощный инструмент с практически бесконечным количеством команд и параметров. Не переживайте, если не можете запомнить их все. Использовать поисковики или заглядывать в шпаргалку — абсолютно нормально. Даже специалисты с большим опытом часто обращаются к интернету, чтобы вспомнить вариации той или иной команды.



# Сделать папку репозиторием — `git init`

Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать **Git-репозиторием** (от англ. *repository* — «хранилище»). Для этого следует переместиться в неё и ввести команду `git init` (от англ. ***init**ialize* — «инициализировать»).

Например, создайте папку `first-project` и сделайте её Git-репозиторием: перейдите в неё с помощью команды `cd` и выполните `git init`.

Скопировать кодBASH

```
$ cd ~/dev/first-project # перешли в нужную папку

$ git init # создали репозиторий 
```

Вы можете создать папку в любом месте на компьютере. Но в этом случае не забывайте менять в наших примерах путь `~/dev/first-project` на тот, который ведёт к вашей папке. Помните, что не рекомендуется создавать репозиторий Git внутри другого Git-репозитория. Это может вызывать проблемы с отслеживанием изменений.

В некоторых случаях при инициализации репозитория Git может показать объёмное сообщение, которое начинается со слов `Using 'master' as the name…`. Не пугайтесь: это не ошибка. Пока это сообщение не имеет большого значения.

💡 **Почему появляется такое сообщение?**

В зависимости от настроек Git может назвать начальную ветку или `main`, или `master`. Сообщение появится в том случае, если ветка по умолчанию будет называться `master`.

После волны протестов [Black Lives Matter](https://blacklivesmatter.com/) многие проекты стали отказываться от терминологии, которая может оскорбить темнокожих людей. Слово **master** можно перевести как «хозяин», поэтому сейчас рекомендуется называть основную ветку `main` (англ. «главная»).

Подробнее о том, что такое ветки и как с ними работать, мы расскажем в дальнейшем.

Также `git init` выведет сообщение вида `Initialized empty Git repository in <*ваша папка с проектом*>/.git/` (англ. «инициализирован пустой Git-репозиторий в `<*ваша папка*>/.git/`»). В подпапке `.git` Git будет хранить всю служебную информацию.

![img](https://pictures.s3.yandex.net/resources/S1_02_02-1_1684836781.png)

Команда `git init` — одна из редко применяемых, ведь репозиторий создаётся один раз, а пользоваться им можно сколько угодно долго.

## «Разгитить» папку, если что-то пошло не так, — `rm -rf .git`

Если вы случайно сделали Git-репозиторием не ту папку, её можно «разгитить». Для этого нужно удалить скрытую подпапку `.git`.

Скопировать кодBASH

```
$ cd <папка с репозиторием> # перешли в папку

$ rm -rf .git # удалили подпапку .git 
```

Разберём подробнее, что такое `-rf`:

- ключ `-r` (от англ. ***r**ecursive* — «рекурсивно») позволяет удалять папки вместе с их содержимым;
- ключ `-f` (от англ. ***f**orce* — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».



## Команда `git status` выведет:

- название текущей ветки: `On branch master` или `On branch main`;
- сообщение о том, что в репозитории ещё нет коммитов: `No commits yet`;
- сообщение, которое говорит: «чтобы что-нибудь закоммитить (то есть зафиксировать), нужно сначала это создать» — `nothing to commit (create/copy files and use "git add" to track)`.

Подробнее о том, что такое коммиты, мы расскажем в следующих уроках.

В отличие от `git init`, команду `git status` используют часто. В любой непонятной ситуации стоит посмотреть состояние (статус) репозитория, а потом решить, что делать дальше.



# Добавляем файлы в репозиторий

Вы инициализировали Git-репозиторий, но в нём пока ничего нет. В этом уроке разберём, как добавить туда файлы.

### Подготовить файлы к сохранению — `git add`

Добавим в репозиторий два файла. Например, файл `todo.txt`, в котором будет список дел, и `readme.txt` для информации о проекте.

📌 **Почему именно текстовые файлы?**

Чаще всего в Git хранят исходный код программ. Но с точки зрения системы контроля версий любой код — это всего лишь текстовый файл. Какой-то специальной логики для хранения программ в ней нет.

Так что Git вполне может быть повседневным инструментом как разработчиков, которые пишут на разных языках программирования, так и администраторов и DevOps, которые, например, работают над файлами конфигураций, или технических писателей, которые создают документацию, и так далее.

Чтобы сделать наши примеры универсальными, мы будем использовать именно текстовые файлы.

Создайте файлы `todo.txt` и `readme.txt` в папке `first-project` и запустите `git status`, чтобы посмотреть, что изменилось.

Скопировать кодBASH

```
$ touch todo.txt
$ touch readme.txt
# создали файлы todo.txt и readme.txt

$ git status # проверили статус 
```

Git сообщит, что в папке `first-project` есть `untracked files` (от англ. *track* — «следить», *untracked* — «неотслеженный», «неотслеживаемый») — ещё не отслеживаемые файлы `readme.txt` и `todo.txt`.

![img](https://pictures.s3.yandex.net/resources/S1_02_02-2_1684837801.png)

Состояние `untracked` значит, что Git ещё не хранит информацию о версиях файла и не может отследить, как он изменялся.

Сейчас в `first-project` два файла. Мы хотим отслеживать состояние обоих, поэтому можем использовать команду `git add --all` (от англ. *add* — «добавить» + от англ. *all* — «всё»). Ключ, или флаг, `--all` позволяет подготовить к сохранению все файлы в репозитории.

Скопировать кодBASH

```
$ git add --all # подготовили к сохранению все файлы в репозитории
$ git status # проверили статус 
```

Добавлять файлы можно и по одному, без ключа `--all`.

Скопировать кодBASH

```
$ git add todo.txt
$ git add readme.txt
$ git status 
```

Также можно добавить текущую папку целиком — в этом случае все файлы в ней тоже будут добавлены. Обратиться к текущей папке в Bash позволяет точка (`.`).

Скопировать кодBASH

```
$ git add . # добавить всю текущую папку
$ git status 
```

Вы можете использовать любой из этих вариантов — результат будет одинаковый.

![img](https://pictures.s3.yandex.net/resources/S1_02_02-4_1684837912.png)

Получилось! Файлы, которые отмечены зелёным, теперь отслеживаются и готовы к сохранению. Но сохранения пока не произошло, потому что команда `git add` только запоминает текущее содержимое (контент) файла.

💡 **Чем отличается запоминание от сохранения?**

 Команда `git add` не сохраняет содержимое файлов в репозитории. Само сохранение, или фиксацию состояния файлов, называют **коммитом** (от англ. *commit* — «совершать», «фиксировать»). «Сделать коммит» значит сохранить текущую версию файла. 

 Если провести аналогию, команду `git add` можно сравнить с добавлением товаров в корзину в интернет-магазине, а коммит — с оформлением и оплатой заказа.

Если сейчас отредактировать любой из «зелёных» файлов в папке `first-project`, он перейдёт в состояние `modified` (англ. «изменённый») и будет и в «зелёном», и в «красном» списках. 

Например, откройте файл `todo.txt` в любом редакторе (подойдёт даже блокнот) и напишите в нём: `1. Пройти пару уроков по Git.`.

![img](https://pictures.s3.yandex.net/resources/S1_02_02-2-2_1684837980.png)

Сохраните изменения, а затем снова вызовите команду `git status` в консоли.

![img](https://pictures.s3.yandex.net/resources/S1_02_02-3_1684838017.png)

Файл `todo.txt` теперь есть и в «зелёном», и в «красном» списках:

- зелёным отмечена пустая версия файла — в таком виде он был во время последнего запуска команды `git add`;
- красным отмечена версия с текстом `1. Пройти пару уроков по Git.`.

Чтобы запомнить новое состояние файла, нужно снова ввести команду `git add` и передать в качестве параметра имя изменённого файла или ключ `--all`.

Скопировать кодBASH

```
$ git add todo.txt
# или
$ git add --all 
```

Теперь файл `todo.txt` снова готов к сохранению! Будет сохранена последняя добавленная версия с текстом `1. Пройти пару уроков по Git.`.

![img](https://pictures.s3.yandex.net/resources/S1_02_02-1-2_1684838122.png)

Подробнее о статусах `untracked`, `modified` и других мы расскажем в одном из следующих уроков.

- Команда `git add` позволяет подготовить файл к сохранению.
- Команда `git add --all` подготовит к сохранению сразу все файлы.
- С помощью `git add .` можно добавить в репозиторий текущую папку со всеми файлами.



# Делаем первый коммит

Коммит — это одна из основных сущностей в Git (и в других системах контроля версий). Коммит гарантирует, что изменения будут сохранены в истории и при необходимости к ним можно будет «откатиться». Это как если бы вы могли выполнить операцию `Ctrl+Z` для целой папки (репозитория).

В этом уроке вы сделаете свой первый коммит.

## Выполнить коммит — `git commit`

Сделать коммит можно командой `git commit` c ключом `-m` (от англ. ***m**essage* — «сообщение»), который присваивает коммиту сообщение.

Обычно в таком сообщении поясняется, в чём именно состояли изменения. Это как заметки на полях: благодаря им проще читать и понимать текст. Сообщение коммита выполняет те же функции — улучшает понимание и упрощает навигацию. Оно пишется после ключа `-m` в кавычках.

Например, перейдите в папку `first-project` и выполните коммит со следующим комментарием.

Скопировать кодBASH

```
$ git commit -m ‘Мой первый коммит!’ 
```

После нажатия `Enter` текущая версия файлов будет сохранена в репозитории с сообщением `Мой первый коммит!`. **Коммит** (по названию команды `git commit`) — это по сути список файлов с их контентом.

![img](https://pictures.s3.yandex.net/resources/S1_02_02-5_1684838712.png)

Команда `git commit` выведет информацию о коммите.

- ```
  [master (root-commit) baa3b6e]
  ```

   значит:

  - коммит был в ветке `master`;
  - `root-commit` — это самый первый, или «корневой» (англ. *root*), коммит в ветке, у следующих коммитов такой надписи не будет;
  - `baa3b6e` — сокращённый идентификатор коммита (подробнее об этом мы ещё расскажем).

- ```
  2 files changed, 1 insertion(+)
  ```

   значит:

  - изменились два файла (`readme.txt` и `todo.txt`);
  - одна строка была добавлена (`1. Пройти пару уроков по Git.`).

- Строки вида 

  ```
  create mode 100644 readme.txt
  ```

   — это более подробная информация о новых (добавленных в Git) файлах.

  - `create` (англ. «создать») говорит, что файл был создан. Если бы файл был удалён, на этом месте было бы слово `delete` (англ. «удалить»).
  - `mode 100644` сообщает, что это обычный файл. Также возможны варианты `100755` для исполняемых файлов (например, `что-нибудь.exe`) и `120000` для файлов-ссылок в Linux. Файлы-ссылки не содержат данных сами по себе, а только ссылаются на другие файлы — как «ярлыки» в Windows.

💡 Обратите внимание: после того как вы сделали первый коммит, команда `git status` перестала выводить сообщение `No commits yet` (англ. «ещё нет коммитов»).

### Ещё раз о разнице между `git add` и `git commit`

Сначала команда `git add` сообщает Git, какие именно файлы нужно сохранить и какую их версию. Затем с помощью команды `git commit` происходит само сохранение. 

В прошлом уроке мы сравнили `add` c добавлением товаров в корзину, а `commit` — с заказом. Теперь проведём ещё одну аналогию — с фотографией.

Сначала вы просите друзей встать в ряд — это команда `git add`. И только после того, как все заняли свои места, поправили волосы и улыбнулись, вы нажимаете кнопку и делаете снимок — это команда `git commit`. Сам получившийся снимок и будет коммитом. В нашем случае на этой фотографии с обратной стороны ещё есть подпись «Мой первый коммит!».

![img](https://pictures.s3.yandex.net/resources/Artboard20120copy205_1402x_1684838813.png)

Кстати, `Мой первый коммит!` — всё же не лучший вариант сообщения. Коммит нужно описывать так, чтобы было понятно, какие именно изменения были сделаны. Например: `Добавлено важное дело в TODO`, `Добавлена сортировка имён`, `Исправлена ошибка в цикле` или `Добавлены заготовки рекламных текстов`.



# Просматриваем историю коммитов

В этом уроке разберём, как вывести историю коммитов, — это понадобится для отслеживания того, что происходит в репозитории.

### Просмотреть историю коммитов — `git log`

В самостоятельном задании прошлого урока вы сделали три коммита в ваш репозиторий. Чтобы увидеть их все, введите команду `git log` (от англ. *log* — «журнал [записей]»).

![img](https://pictures.s3.yandex.net/resources/S1_02_02-8_1684923937.png)

Обратите внимание, что по умолчанию `git log` выводит коммиты в обратном хронологическом порядке — последние коммиты оказываются первыми сверху. В этом можно убедиться, если посмотреть на дату и время их создания.

Если после выполнения команды вы видите, что в репозитории есть только один коммит или их нет вообще, вернитесь к прошлому уроку и убедитесь, что `git add` и `git commit` были вызваны в нужном порядке.



# Знакомство с GitHub

До этого момента вы использовали Git **локально**: сейчас проект `help_git` хранится только на вашем компьютере. Но одно из ключевых преимуществ Git — удобство командной работы над файлами. Чтобы поделиться репозиторием — например, с коллегами, — нужно завести его **удалённую версию**. 

Процесс командной работы может выглядеть так: вы работаете над файлами проекта, например пишете код, на своём компьютере и сохраняете в локальном репозитории. Как только накапливается достаточно правок, чтобы поделиться ими с остальными, вы передаёте их на удалённый репозиторий. Там ваши коллеги смогут посмотреть то, что получилось, и даже скачать себе на компьютер.

![img](https://pictures.s3.yandex.net/resources/S1_02_03_1684925317.png)

Есть несколько платформ для такой командной работы. Самая популярная — GitHub. В нескольких следующих уроках покажем, как с ней работать. 

## Что такое GitHub

[GitHub](https://github.com/) — платформа для хранения IT-проектов и совместной работы над ними с использованием Git. По сути, это сайт, куда можно загрузить файлы своего проекта для обмена с другими людьми.

С английского языка слово **hub** переводится как «узловая станция». И действительно, GitHub стал самым популярным сайтом для хранения Git-репозиториев. Многие крупные компании, такие как Google, Apple, Valve, используют GitHub для своих проектов. 

GitHub подходит, чтобы отточить навыки работы с Git. Здесь можно завести аккаунт и вместе со своей командой работать над любыми задачами. Можно создавать проекты разных типов: 

- приватный — только для вас;
- командный — только для членов команды;
- публичный — будет виден всем.

Также можно присоединиться к чужому open source проекту и работать над ним вместе с другими людьми со всего мира. 

А ещё GitHub — это социальная сеть для разработчиков. С момента своего возникновения в 20082008 году она, [согласно статистике](https://octoverse.github.com/), объединила десятки миллионов человек, дала им возможность для реализации идей и сотрудничества.



## Git и платформы для удалённой работы

Git и GitHub — это два разных проекта, которые развиваются независимо друг от друга. 

Git: - консольный инструмент для работы с локальными и удалёнными репозиториями; - проект с открытым исходным кодом.

GitHub: - платформа для размещения удалённых репозиториев; - принадлежит компании Microsoft.

Кроме GitHub, есть и другие платформы для командной работы. Например, GitLab и Bitbucket, которые тоже позволяют работать с Git. У каждой из этих платформ свои особенности и дополнительная функциональность: - GitLab можно развернуть в виде сервера в приватной сети; - Bitbucket — продукт компании Atlassian, поэтому он легко интегрируется с другими инструментами этой компании, такими как Jira.

В этом курсе вы будете взаимодействовать с GitHub. Но в целом эти платформы похожи, и если вы изучите одну из них, то переход на другую не будет проблемой.

💡 **Можно ли делать сложные проекты без GitHub?**

Такие платформы, как GitHub, Bitbucket и другие, значительно упрощают процесс командной работы. Но при этом Git может использоваться и без них для создания даже больших проектов.  

Например, ядро Linux — самой популярной операционной системы для серверов, телефонов и суперкомпьютеров — разрабатывают с помощью **патчей** (от англ. *patch* — «заплата», «лоскут»). Это файлы, которые содержат отличия исходной версии от последующих.  

Такие патчи рассматривает и объединяет в основную версию ядра лично Линус Торвальдс — создатель Linux и Git. Это происходит без использования средств платформ вроде GitHub.



# Создаём удалённый репозиторий

В прошлом уроке вы завели аккаунт на GitHub. Теперь разберём, как создать удалённый репозиторий, чтобы в будущем связать его с локальным.

## Инструкция по созданию репозитория на GitHub

1. Зайдите в свой профиль по ссылке `https://github.com/username`, где `username` — имя, которое вы указали при регистрации. Эта страница — презентация вас и ваших проектов. Её видят другие пользователи. Надпись **You don't have any public repositories yet** (англ. «у вас пока нет публичных репозиториев») сообщает, что пока у вас нет проектов.

![img](https://pictures.s3.yandex.net/resources/S1_02_03-1-2_1684935796.png)

1. Создайте репозиторий. Для этого перейдите на вкладку **Repositories** (англ. «репозитории»), а затем нажмите на зелёную кнопку **New** (англ. «новый») справа.

![img](https://pictures.s3.yandex.net/resources/S1_02_03-3_1684935815.png)

1. Открылось окно создания нового репозитория. Назовите его `help_git_yandex`. Название удалённого репозитория необязательно должно совпадать с именем папки проекта у вас на компьютере. Но чтобы не путаться, будем называть их одинаково. Другие поля вам пока не понадобятся. Смело нажимайте на зелёную кнопку **Create repository** (англ. «создать репозиторий») внизу.

![img](https://pictures.s3.yandex.net/resources/S1_02_03-3-2_1684935833.png)

Готово! Удалённый репозиторий создан. Страница с ним открывается автоматически. 

![img](https://pictures.s3.yandex.net/resources/S1_02_03-2-3_1684935849.png)

Осталось связать удалённый репозиторий с локальным, который уже есть на вашем компьютере. GitHub предоставляет для этого инструкцию (пункт `…or push an existing repository from the command line`).



# Что такое SSH. Генерируем SSH-ключ

Представьте, что у вас есть ключ от двери, за которой хранится важный документ. Чтобы получить доступ к этому документу, вам нужно вставить ключ в замочную скважину и повернуть его. Поскольку ключ есть только у вас, ваш документ надёжно защищён от посторонних глаз.

Чтобы получить доступ к репозиторию на GitHub, вам тоже нужно предоставить ключ, который подтверждает вашу личность и права на чтение или изменение данных. Без этого ключа доступ будет ограничен. Об этом и пойдёт речь в уроке.

## Что такое SSH

Когда компьютеры обмениваются данными в сети, они следуют **сетевым протоколам** (англ. *network protocols*) — правилам обмена данными между компьютерами.

Один из наиболее распространённых сетевых протоколов — **SSH** (от англ. ***S**ecure **Sh**ell Protocol*). Он обеспечивает безопасный обмен данными в сети. С помощью этого протокола можно получать данные с удалённого компьютера или отправлять их на него. Трафик шифруется, поэтому протокол безопасен.

SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 

- **Приватный ключ** (англ. *private key*) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных.
- **Публичный ключ** (англ. *public key*) доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.

Только вы можете расшифровать данные с помощью приватного ключа, но любой владелец публичного ключа может их для вас зашифровать. Эти два ключа связаны и образуют **SSH-пару**. В будущем вы наверняка будете использовать их для взаимодействия с GitHub и другими удалёнными серверами.

## Проверка наличия SSH-ключа

Прежде чем генерировать SSH-ключи, убедитесь, что у вас их ещё нет. По умолчанию директория с SSH-ключами находится в домашней директории пользователя. Перейдите в неё.

```
$ cd ~ # перешли в домашнюю директорию 
```

Обычно SSH-ключи находятся в директории `.ssh/`. Проверить наличие этой директории и файлов в ней можно с помощью следующей команды.

```
$ ls -la .ssh/ # вывели список созданных ключей 
```

Если папка пустая или её нет, всё в порядке. 

Если есть файлы с похожими названиями, SSH-ключи уже создавались:

- `id_dsa.pub`;
- `id_ecdsa.pub`;
- `id_ed25519.pub`;
- `id_rsa.pub`.

Если вы не создавали эти файлы, удалите их все.

## Инструкция по генерации SSH-ключа

1. Для генерации SSH-пары можно использовать программу `ssh-keygen`. Откройте терминал и введите следующую команду.

Скопировать кодBASH

```
$ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" 
```

​    Используйте электронную почту, к которой привязан ваш GitHub-аккаунт.

​    Если вы видите сообщение об ошибке, то, скорее всего, ваша система не поддерживает алгоритм шифрования `ed25519`. Ничего страшного: используйте другой алгоритм.

Скопировать кодBASH

```
$ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" 
```

​    После ввода отобразится такое сообщение.

```
> Generating public/private rsa key pair. # сгенерированы публичный и приватный ключи 
```

1. Укажите место хранения ключей. Простой вариант — сделать домашний каталог пользователя путём по умолчанию. Для этого нажмите `Enter`.

   ### **macOS**

```
> Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter] 
```

### **Windows**

```
> Enter a file in which to save the key (C:\Users\<имя_пользователя>\.ssh\):[Press enter] 
```

​    Теперь в указанной директории появится пара ключей.

1. Программа запросит **кодовую фразу** (англ. *passphrase*) для доступа к SSH-ключу. Вы можете оставить поле пустым. Для этого нажмите `Enter`, а затем ещё раз `Enter` для подтверждения.

Скопировать кодBASH

```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again] 
```

💡 **Быть или не быть кодовой фразе — вот в чём вопрос**

Как бы странно ни звучало, кодовая фраза — это «пароль от ключа». Представьте, что SSH-ключ лежит в шкатулке. А на самой шкатулке — кодовый замок, который открывается кодовой фразой.

Многие пользователи Git не используют кодовую фразу для защиты своего SSH-ключа. Если такой фразы нет, то её не нужно вводить всякий раз при взаимодействии с удалённым репозиторием.

С другой стороны, применение кодовой фразы усиливает безопасность ключей. Если вы используете эту фразу, ключ будет надёжно защищён в случае несанкционированного доступа к вашему компьютеру.

1. Готово! Теперь осталось проверить, что ключи действительно сгенерировались. Для этого вызовите эту команду.

Скопировать кодBASH

```
ls -a ~/.ssh 
```

​    На экране должны появиться два файла — один с расширением `.pub`, другой — без. Файл в `.pub` — публичный, им можно делиться с веб-сайтами или коллегами. Файл без расширения `.pub` — приватный. Ни в коем случае не передавайте его никому! 

​    Вся последовательность действий в консоли показана на скриншоте ниже.

![img](https://pictures.s3.yandex.net/resources/M2_T4_01_1684937563.png)



# Привязываем SSH-ключ к GitHub

В прошлом уроке вы сгенерировали SSH-ключ, но он пока не привязан к аккаунту на GitHub. Исправим это.

## Инструкция по связыванию SSH-ключа и GitHub-аккаунта

1. После выполнения команды 

   ```
   ssh-keygen
   ```

    из предыдущего урока в директории 

   ```
   ~/.ssh
   ```

    будет создано два файла — 

   ```
   id_ed25519
   ```

    и 

   ```
   id_ed25519.pub
   ```

    (или 

   ```
   id_rsa
   ```

    и 

   ```
   id_rsa.pub
   ```

    — в зависимости от того, какой алгоритм вы использовали):

   - `id_ed25519`/`id_rsa` — приватный ключ (файл без `.pub` в конце). Ни в коем случае не копируйте его и не делитесь им.

   - `id_ed25519.pub`/`id_rsa.pub` — публичный ключ (на это указывает расширение `.pub`).

     Скопируйте содержимое файла с публичным ключом в буфер обмена.

### **macOS**



```
# скопировать содержимое ключа в буфер обмена:
$ pbcopy < ~/.ssh/id_rsa.pub
# для ed25519:
$ pbcopy < ~/.ssh/id_ed25519.pub 
```

Здесь используется команда `pbcopy` — она копирует поток данных в буфер обмена. Запись `pbcopy < ~/.ssh/id_rsa.pub` означает: «Скопируй в буфер обмена всё содержимое файла `~/.ssh/id_rsa.pub`».

В качестве альтернативы вы можете распечатать файл на экран с помощью `cat ~/.ssh/id_rsa.pub` и скопировать его вручную.

### **Windows**



```
# скопировать содержимое ключа в буфер обмена:
$ clip < ~/.ssh/id_rsa.pub
# для ed25519:
$ clip < ~/.ssh/id_ed25519.pub 
```

Если `clip` не сработает, выведите содержимое файла с помощью `cat ~/.ssh/id_rsa.pub` или `cat ~/.ssh/id_ed25519.pub` и скопируйте вывод в буфер обмена из консоли.

1. Перейдите на GitHub и выберите пункт **Settings** (англ. «настройки») в меню аккаунта.

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_01_1685016747.png)

1. В меню слева нажмите на пункт **SSH and GPG keys**.

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_02_1685016772.png)

1. В открывшейся вкладке выберите **New SSH key** (англ. «новый SSH-ключ»).

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_03_1685016795.png)

1. В поле **Title** (англ. «заголовок») напишите название ключа. Например, **Personal key** (англ. «личный ключ»).
2. В поле **Key type** (англ. «тип ключа») должно быть **Authentication Key** (англ. «ключ аутентификации»).
3. В поле **Key** скопируйте ваш ключ из буфера обмена.

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_04_1685016816.png)

\8. Нажмите на кнопку **Add SSH key** (англ. «добавить SSH-ключ»).

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_05_1685016840.png)

1. Проверьте правильность ключа с помощью следующей команды.

```
$ ssh -T git@github.com 
```

Если это первый раз, когда вы используете Git, чтобы поделиться проектом на GitHub, появится похожее предупреждение.

```
The authenticity of host 'github.com (140.82.121.4)' can't be established. ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU. This key is not known by any other names. Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```

Это предупреждение сообщает, что вы никогда не соединялись с сервером GitHub. Поэтому Git не может гарантировать, что сервер является тем, за кого он себя выдаёт.

Для подтверждения подлинности сервер генерирует и публикует ключи SHA256. Вы можете проверить ключи GitHub [по этой ссылке](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints). Если ключ в предупреждении совпадает с тем, что вы видите на сайте, значит, сервер является действительным. Введите `yes`, чтобы продолжить. Вы увидите приветствие на экране.

```
Hi %ВАШ_АККАУНТ%! You've successfully authenticated, but GitHub does not provide shell access. 
```

Если у вас возникли сложности при генерации или привязке SSH-ключей, посмотрите видеоинструкцию, в которой мы показываем всё по порядку.



Посмотреть видеоинструкцию по генерации и привязке SSH-ключей

Выберите, какие из перечисленных ключей являются публичными.

Правильный ответ

```
id_rsa.pub
```

Это публичный ключ с расширением `.pub`.



```
id_rsa
```

Если у ключа нет расширения, это приватный ключ. Таким ключом нельзя ни с кем делиться!



```
ssh_key
```

Это приватный ключ. Никогда не делитесь им!

Правильный ответ

```
my_key.pub
```

Расширение `.pub` указывает на то, что ключ публичный.



```
ssh_key.pab
```

Расширения `.pab` не существует.

Ура: теперь ваш ключ привязан к GitHub! Если вы установили кодовую фразу для SSH-ключа, её нужно будет вводить для работы с репозиторием



# Связываем локальный и удалённый репозитории

Сейчас у вас есть локальный репозиторий `first-project`, который хранится на вашем компьютере, и удалённый репозиторий на GitHub. Вы сгенерировали SSH-ключ для безопасной работы и теперь готовы связать удалённый репозиторий с локальным.

![img](https://pictures.s3.yandex.net/resources/Artboard20120copy206_1402x_1685021899.png)

## Привязать удалённый репозиторий к локальному — `git remote add`

Перейдите на страницу удалённого репозитория, выберите тип `SSH` и скопируйте URL. Кнопка справа позволит сделать это мгновенно.

![img](https://pictures.s3.yandex.net/resources/M2_T4_02_1685021914.png)

Откройте консоль, перейдите в каталог локального репозитория и введите команду `git remote add` (от англ. *remote* — «удалённый» и *add* — «добавить»).

Скопировать кодBASH

```
$ cd ~/dev/first-project
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git 
```

Команде необходимо передать два параметра: имя удалённого репозитория и его URL. В качестве имени используйте слово `origin`. А URL вы скопировали со страницы удалённого репозитория.

💡 **Как выполнить вставку в командную строку?**

В командную строку нельзя вставить текст из буфера обмена с помощью привычного сочетания `Ctrl+V`. На Windows (в Git Bash) и Linux для этого используется сочетание `Ctrl+Shift+V`, а на macOS — `Cmd+V`.

Также можно нажать правую кнопку мыши и выбрать пункт **Paste** (англ. «вставить») в выпадающем меню.

`origin` (англ. «источник») — стандартный псевдоним, с помощью которого можно обращаться к главному удалённому репозиторию (обычно такой репозиторий один). Это значительно упрощает работу.

## Убедиться, что репозитории связаны, — `git remote -v`

Отлично: вы связали локальный репозиторий с удалённым. Осталось убедиться, что всё работает, с помощью следующей команды.

Скопировать кодBASH

```
$ git remote -v
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push) 
```

В выводе вы должны увидеть две строчки, аналогичные тем, что показаны выше.

Флаг `-v` — короткая форма флага `--verbose` (англ. «подробный»). Он позволяет показать больше информации в выводе.



# Синхронизируем локальный и удалённый репозитории

Вы зарегистрировались на GitHub, сгенерировали SSH-ключ и привязали локальный репозиторий к удалённому. Самое сложное позади! Теперь разберём, как выкладывать свои правки на удалённый репозиторий. Но сначала немного о ветках.

## Основная ветка

Мы упоминали, что каждый коммит сохраняет актуальное состояние файлов. Сами же коммиты хранятся в **ветках** (англ. *branch*).

Если коммит — это снимок состояния файлов, то ветка — временна́я шкала, на которой расположены эти снимки. Ветка всегда начинается от одного из коммитов.

В репозитории может существовать сразу несколько веток — параллельных историй изменений. Также они могут соединяться друг с другом.

![img](https://pictures.s3.yandex.net/resources/M2_T4_01-2_1685963656.png)

Самая первая ветка в репозитории появляется автоматически и называется `main` (англ. «основная») или `master`. Её имя нужно указывать при отправке коммитов на удалённый репозиторий или при получении их из него.

💡 **`main` или `master`?**

Раньше основная ветка в репозиториях, созданных на GitHub, называлась `master`, но с 11 октября 20202020 года (после волны протестов движения Black Lives Matter) её переименовали в `main`. 

Во всех репозиториях, созданных раньше этой даты, название основной ветки не поменялось. Поэтому в проектах, которые начали именно с `master`, и в руководствах по работе с Git вы по-прежнему можете встретить имя `master`. 

## Отправить изменения на удалённый репозиторий — `git push`

Вы уже прошли весь «цикл коммита»: подготовили файлы с помощью `git add`, закоммитили их с комментарием командой `git commit -m`. Осталось загрузить содержимое локального репозитория на GitHub. За это отвечает команда `git push` (от англ. *push* — «толкать»).

В первый раз эту команду нужно вызвать с флагом `-u` и параметрами `origin` (имя удалённого репозитория) и `main` или `master` (название текущей ветки). Флаг `-u` свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории в предыдущем уроке, так же и здесь нужно дополнительно связать ветки.

Скопировать кодBASH

```
$ git push -u origin main # Если команда приведёт к ошибке, попробуйте 
                          # заменить main на master. 
```

Появится такой экран.

![img](https://pictures.s3.yandex.net/resources/M2_T4_02-2_1685963722.png)

При взаимодействии с удалёнными репозиториями Git выводит в консоль отладочную информацию: количество объектов (файлов), которые отправляются на сервер, информацию о прогрессе сжатия и записи и так далее.

Если вы указывали кодовую фразу при настройке SSH-ключей, её нужно будет ввести.

Зайдите в репозиторий `first-project` на GitHub. Вы увидите, что в репозитории появились файлы с изменениями.

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_01-2_1685963748.png)

В дальнейшем при работе с удалённым репозиторием флаг `-u` можно опустить и писать просто `git push`.

### Работа с графическим интерфейсом GitHub

GitHub предоставляет удобный интерфейс для работы с репозиторием. Например, нажмите на кнопку **commit** в правой части страницы, чтобы просмотреть все коммиты в репозитории.

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_02-2_1685963765.png)

Откроется окно с коммитами и их авторами.

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_03-2_1685963782.png)

Сообщение коммита в репозитории тоже является ссылкой. 

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_04-2_1685963797.png)

Перейдите по ссылке, кликните на текст последнего коммита над репозиторием — так вы сможете увидеть все изменения, которые были внесены в репозиторий в этом коммите.

![img](https://pictures.s3.yandex.net/resources/M2_T4_03_05-2_1685963809.png)

## Задание для самостоятельной работы

1. Откройте проект `first-project` и создайте в нём файл `task.txt` с помощью `touch`.
2. Откройте файл `task.txt` в текстовом редакторе и внесите любые изменения. Затем сохраните и закройте файл.
3. Сделайте коммит и синхронизируйте изменения с удалённым репозиторием.

Скопировать кодBASH

```
$ git push 
```

1. Воспользуйтесь интерфейсом GitHub, чтобы посмотреть ваш последний коммит. Для этого нажмите на имя коммита.

Теперь ваши изменения могут увидеть те, кому вы отправите ссылку на проект!

Копилка ваших знаний о Git постепенно пополняется! Вот о чём мы рассказали:

- Коммиты хранятся в ветках. Начальная ветка создаётся автоматически и называется `main` или `master`.
- За отправку изменений на удалённый репозиторий отвечает команда `git push`.
- Интерфейс GitHub позволяет удобно просмотреть все коммиты в репозитории, а также изменения в этих коммитах.