# Домашнее задание к занятию «Системы контроля версий»
    Задание 1. Создать и настроить репозиторий для дальнейшей работы на курсе
Создание репозитория и первого коммита

1. Создадим новый репозиторий на GitHub:

![](Screenshot's/create_repo.png)

2. Склонируем репозиторий (git clone):

![](Screenshot's/copy_repo.png)
3. Так как я уже настраивал имя пользователя и email пользователя, я выведу их командами (git config user.name)&(git config user.email):

![](Screenshot's/User.name_and_email.png)
4. Переведем файл README.md в состояние modified. Для этого произведем изменения в файле README.md и выполним команду git status:

![](Screenshot's/readme_modified.png)
после выполнения команды (git status) видно что, git присвоил статус modified файлу README.md
5. Далее я ввел команду (git diff) и (git diff --staged) но, так как я не понимал сути этих команд ввел их одну за одной)

![](Screenshot's/git_diff_and_git_staged.png)

разобравшись в смылсе этих команд понял, что команда (git diff) необходима для того что бы просмотреть изменения до внесения в стейджинг, поэтому команда (git diff --staged) не вывела никаких результатов. Команда (git diff --staged) необходима для сравнения изменений внесенных в стейджинг с последним коммитом.
6. Произведя изменения в файле README.md переведем этот файл в состояние стейджинг командой (git add):

![](Screenshot's/add_readme_and_git_status.png)
Можем видеть что файлу README.md присвое статус modified, а папка Screenshot's находиться в состоянии Untracked так как, она была создана после создания репорзитория.

7. Теперь повторно введем команду (git dif --staged) и получим следующий ввывод:
![](Screenshot's/git_diff_--staged.png)
Видим что команда показывает какие изменения быле внесены между стейджингов.

8. Выполним коммит c коментарием командой (git commit -m 'First commit'), но так как я не внес в стейджинг папку со скриншотами, мне пришлось делать коммит два раза. Следующий коммит был с коминтарием (First commit + screenshot):
![](Screenshot's/commit_f_f+s.png)

    
    Создание файлов .gitignore и второго коммита
1. Создадим файл .gitignore командой (touch .gitignore) и проверим успех выполнения команды другой командой (ls -a), ну или включим функцию просмотра скрытых файлов в папках.
![](Screenshot's/touch_igno.png)
![](Screenshot's/papka.png)
2. Добавляем файл .gitignore в следующий коммит (git add .gitignore) и проверяем командой (git status) в каком состоянии файл .gitignore
![](Screenshot's/commit_igno.png)
![](Screenshot's/status_igno.png)
3. Создадим папку terraform командой (mkdir terraform) и так же проверим выполнение команды с помощью команды (ls -a)
![](Screenshot's/tera_papka.png)
Видим что мы успешно создали папку под названием terraform
4. Создадим файл .gitignore в папке terraform и отредактируем его с помощью редактора nano, вставим в файл записи из [Terraform.gitignore](https://github.com/github/gitignore/blob/main/Terraform.gitignore)
![](Screenshot's/nano_igno.png)

Из вставленных записей можем видеть что в будущем мы с помощью этого файла будем игнорировать файлы:

/.terraform/ - Это локальные папки terraform;

.tfstate - файлы состояний; 

.crash.log - файлы ошибок;

.tfvars - файлы с личной информацией;

override.tf - я не знаю зачем они нужны

.terraform.rc - файлы конфигурации сети

