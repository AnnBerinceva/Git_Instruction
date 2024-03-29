# Инструкция по работе с системой контроля версий GIT

## Часть I - Знакомство с контролем версий (GIT)

*Контроль версий (GIT)* - это программа, которая берёт на себя вопросы контроля версий над проектом. 
+ сохраняет в памяти не файлы целиком, а разницу между файлами
+ программа, которая позволяет отслеживать изменения исходного кода и управлять ими.
+ это возможность хранить различные версии проекта.
+ GIT позволяет возвращаться к различным версиям проекта, перемещаться между ними. 
+ хранение версий сводится к созданию копий информации на сервере.
+ функция возврата реализуется за счет восстановления предыдущих версий.

### С чего начать работу с GIT?

1. Установка программы: необходимо установить сам Git, используя установщик, в зависимости от операционной системы. Скачиваем GIT по ссылке:

    [ссылка на GIT](https://git-scm.com/downloads) 

    Также для работы с GIT нам потребуется программа редактирования Visual Studio Code:

    [ссылка на VS Code](https://code.visualstudio.com/)

2. Далее необходимо зарегистрироваться в git, представиться ему. Это нужно сделать один раз, в самом начале работы с программой:

    git config --global user.name "Ваше имя"

    git config --global user.email ваша_почта@example.com

3. Чтобы начать отслеживать изменения в проекте, необходимо где-то хранить все файлы. Для этого нужно создать репозиторий: 

        3.1. Cоздать папку на рабочем столе и дать ей имя.
        3.2. Запустить программу «Visual Studio Code».
        3.3. Затем, в левом верхнем углу найти проводник, нажать на него.
        3.4. После этого нажать на строку «Открыть папку». Найти "нужную папку" и нажать «Открыть».
        3.5. Запустить терминал (в меню пункт "Вид" выбрать "Терминал" и нажать на него).

4. Необходимо проверить, что «GIT» настроен, т.е. вывести текущую версию на экран, командой:

    git —version

5. Теперь необходимо инициализировать папку, сделать ее репозиторием, командой:

    git init

6. Чтобы узнать текущий СТАТУС, вызываем команду

    git status

Итак, новый репозиторий создан. Теперь в папке появилась новая скрытая папка, в которой будут храниться все изменения, которые будут вноситься в файл на терминале. 

### Cоздание нового файла:

1. Правой кнопкой мыши нажать в левом окне и выбрать "Создать файл".
2. Написать название файла (на английском языке), поставить точку и выбрать расширение (.md, .txt, .doc и т.д.). 
3. В окне справа для ввода текста, написать текст и сохранить его (Ctrl+S).   
    Для сохранения текста, чтобы постоянно не нажимать на (Сtrl+s) в файл, выбрать автосохранение.
4. Указать текущий статус (git status).   
5. Git показывает, что у есть неотслеживаемый файл. 
6. Для того, чтобы GIT начал отслеживать изменения в файле, необходимо их добавить. 

    *git add «имя файла с точкой и расширением»*

    Если никаких сообщений об ошибках нет, значит всё прошло успешно. 

*При введении имени файла достаточно набрать первые несколько букв из названия файла и нажать Tab, Git самостоятельно подставит имя файла в команду.* 

7. Снова проверить статус документа, командой *git status*. 
Git начал отслеживать документ, сообщения об ошибке нет, значит, все в порядке, все действия выполнены правильно. 
8. Необходимо закоммитить все произведенные изменения в файл, командой: 

    git commit -m"сообщение о внесенных изменениях"
9. Затем, нужно проверить правильность внесенных изменений (git status).
10. При внесении любых изменений в файл (в поле ввода справа) нужно также их добавить в файл (git add *имя файла*) и закоммитить (*git commit -m"инф об изменениях"*).

### Работа с файлом и коммитами

   + В документе есть два коммита, с которыми можно работать. Можно переходить от одной версии файла к другой, чтобы понять какие версии существуют. Для этого есть специальная команда - журнал версий:

        git log
  

+ Появляется сообщение о том, что есть некоторая фиксация, т.е. некоторые сохранения. И у каждого из этих сохранений есть свой текстовый комментарий.

+ Если нужно перейти к предыдущей версии этого файла, использовать команду 

    git checkout первые 4 цифры нужного коммита
+ Для возвращения обратно к версии с уже всеми внесенными коммитами, нужно ввести эту же команду, но с цифрами поледнего коммита. 

#### **Это весь путь создания файла и внесения изменений в него**


### Команды GIT
1. ↑ и ↓: позволяет переключаться между ранее введенными командами в терминале.
2. git add: добавление содержимого в рабочий файл.
3. git commit -m"информация об изменениях": фиксация текущего статуса, сохранение изменений.
4. git status: показывает текущее состояние Git.
5. git log: журнал изменений.
6. git checkout: переключение между существующими версиями/ветками.
7. q: возвращение в исходное окнотерминала.
8. git init: инициализация папки/файла. 
9. git diff: показывает разницу между текущим файлом и сохраненным. 
10. git version: проверка текущей версии Git. 
11. clear: очищение поля ввода в терминале. 
12. git help: покаывает команды git.

## Часть II - Работа с ветками в Git

*Ветка (branch)* -это черновики программы.

+ параллельно можно создавать несколько веток и работать в них одновременно.
+ ветки нужны для выполнения отдельных задач.
+ ветки - это параллельные версии, которые можно создавать для внесения изменений или исправлений. 
+ работа в неосновной ветке никак не влияет на основную ветку (master/main), не вносит в нее никаких изменений. 

### Команды для работы с ветками: 

 1. git branch: показывает все существующе ветки программы. 
 2. git branch *название*: создание новой ветки.
 3. git checkout *название ветки*: переключение на определенную ветку. 
 4. git merge: слияние веток.
 5. git branch -d *название ветки*: удаление ненужной ветки. 
 6. .gitignore: это файл, создается в окне слева. Нужен для указания файла, который необходимо игнорировать. 
 7. git log --graph: визуализация всех коммитов в виде дерева. 

### Создание конфликта версий 
 + конфликт веток возникает при слиянии веток с разной информацией, т.е. когда текст в 1 ветке не совпадает с текстом в другой ветке. 
 + Git самостоятельно не может решить какую ветку считаь. Он предлагает 3 варианта решения конфликта: 
    
    1. принять текущую версию (current change).
    2. принять входящие изменения (incoming change).
    3. принять и сохранить оба варианта.

    **У репозитория должен быть один человек, который будет решать такие конфликты.**

## Часть III - Работа с удаленными репозиториями.

*Удаленные репозитории - это репозитории, находящиеся не на личном компьютере и располагающиеся удаленно на сервере или другом компьютере.* 

Сервис Git Hub и программа Git 

| Git Hub       | Git           |
| ------------- |:-------------|
| сервис компании Microsoft| программа, которая устанавливается на компьютер|
| позволяет интегрироваться с Git  | выполняет локальную работу с проектом       |
| настраивает удаленную работу с репозиторием |одна из систем контроля версий       |

**Можно работать локально или хранить свой репозиторий на Git Hub, используя команды Git.**

### Как взять готовый репозиторий с Git Hub?
 + найти через поиск на Git Hub автора или сам проект
+ проект можно посмотреть на самом сайте
+ через кнопку Code зеленого цвета можно скопировать адрес проекта
+ скопировать эту ссылку и вставить в Git
+ копирование ссылки происходит по команде 
    
    *git clone **скопированный адрес***


    Это составная команда, она загружает все изменения и пытается слить все ветки. 
+ после этого произойдет копирование репозитория на локальный компьютер. 

### Перенос локального репозитория на Git Hub
1. создать аккаунт на Git Hub
2. выбрать новый репозиторий и дать ему имя
3. Git Hub предложит три варианта действий: создать новый репозиторий через терминал, привязать существующий репозиторий к удаленному, импортировать код из другого репозитория. 
4. в локальном репозитории ввести команду:

    git remote add origin *ссылка с Git Hub*

5. указать ветку, которая будет основной (main)
6. использовать команду, которая "протолкнет" все локальные изменения на удаленный репозиторий

    git push

7. при первом связывании Git Hub и Git их необходимо будет "подружить", выполнить авторизацию

    git push -u origin main

### Работа с публичным репозиторием

+ должна быть надпись "public" у репозитория на Git Hub
+ синхронизация версии с Git Hub на локальный репозиторий 

    git pull 

Команда попытаетcя слить ветки в одну. 

### Работа программистов

+ обычно создают 1 аккаунт, основной репозиторий (доступ имеет ограниченный круг лиц)
+ инструмент в Git, который позволяет другим людям вносить изменения в проект 

    pull request 

Это запрос на вливание в репозиторий. 
+ На Git Hub можно сделать копию репозитория. Эта кнопка делает полную копию репозитория на личный аккаунт, с которой можно работать. 

    Fork - это ответвление от начального проекта. 
+ можно клонировать указанный репозиторий на локальный компьютер. 
+ у каждого проекта на Git Hub должен быть файл READ.ME, в котором указывается описание того, что происходит внутри проекта. 
+ файл READ.ME создается локально в VS Code, внутри папки на отдельной ветке (например, description).

### Создание кнопки Pull Request

+ команда для предложения изменений 
+ запрос на вливание в репозиторий

1. делаем Fork (ответвление) репозитория
2. делаем git clone своей версии репозитория 
3. создаем новую ветку и в нее добавляем изменения
4. производим все изменения толь в этой ветке
5. отправить изменения на свой аккаунт
6. на Git Hub нажать кнопку Pull Request