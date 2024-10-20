# Работа с git

## Навигация
* pwd (от англ. *print working directory*, «показать рабочую папку») — покажи, в какой я папке;  
* ls (от англ. *list directory contents*, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;  
* ls -a — покажи также скрытые файлы и папки, названия которых начинаются с символа .;  
* cd first-project (от англ. *change directory*, «сменить директорию») — перейди в папку first-project;  
* cd first-project/html — перейди в папку html, которая находится в папке first-project;  
* cd .. — перейди на уровень выше, в родительскую папку;  
* cd ~ — перейди в домашнюю директорию (/Users/Username);  
* cd / — перейди в корневую директорию.  
  
## Работа с файлами и папками  
1. Создание
* touch index.html (англ. *touch*, «коснуться») — создай файл index.html в текущей папке;
* touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
* mkdir second-project (от англ. *make directory*, «создать директорию») — создай папку с именем second-project в текущей папке.
2. Копирование и перемещение
* cp file.txt ~/my-dir (от англ. *copy*, «копировать») — скопируй файл в другое место;
* mv file.txt ~/my-dir (от англ. *move*, «переместить») — перемести файл или папку в другое место.
3. Чтение
* cat file.txt (от англ. *concatenate and print*, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.
4. Удаление
* rm about.html (от англ. *remove*, «удалить») — удали файл about.html;
* rmdir images (от англ. *remove directory*, «удалить директорию») — удали папку images;
* rm -r second-project (от англ. *remove*, «удалить» + *recursive*, «рекурсивный») — удали папку second-project и всё, что она содержит.
5. Полезные возможности
* Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).
* У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).
* Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.  Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab.  Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.
6. Инициализация репозитория
* git init (от англ. *initialize*, «инициализировать») — инициализируй репозиторий.
7. Подготовка файла к коммиту
* git add todo.txt (от англ. *add*, «добавить») — подготовь файл todo.txt к коммиту;
* git add --all (от англ. *add*, «добавить» + *all*, «всё») — подготовь к коммиту сразу все файлы, в которых были изменения, и все новые файлы;
* git add . — подготовь к коммиту текущую папку и все файлы в ней.
8. Создание коммита
* git commit -m "Комментарий к коммиту." (от англ. *commit*, «совершать», «фиксировать» + *message*, «сообщение») — сделай коммит и оставь комментарий, чтобы было проще понять, какие изменения внесены. 
9. Просмотр информации о коммитах
* git log (от англ. *log*, «журнал [записей]») — выведи подробную историю коммитов.
10. Просмотр состояния файлов
* git status (от англ. *status*, «статус», «состояние») — покажи текущее состояние репозитория.

## Синхронизация локального и удалённого репозиториев
* git remote add origin https://github.com/YandexPracticum/first-project.git (от англ. remote, «удалённый» + add, «добавить») — привяжи локальный репозиторий к удалённому с URL https://github.com/YandexPracticum/first-project.git;
* git remote -v (от англ. verbose, «подробный») — проверь, что репозитории действительно связались;
* git push -u origin main (от англ. push, «толкать») — в первый раз загрузи все коммиты из локального репозитория в удалённый с названием origin.
**💡 Ваша ветка может называться master, а не main. Подправьте команду, если это необходимо.**
* git push (от англ. push, «толкать») — загрузи коммиты в удалённый репозиторий после того, как он был привязан с помощью флага -u.

## Копирование чужих репозиториев
1. Клонирование
* git clone git@github.com:TheGreatOwner/the-great-project.git (от англ. clone, «клон», «копия») — склонируй репозиторий с URL the-great-project.git из аккаунта TheGreatOwner на мой локальный компьютер.
2. «Форк»
* «Форк» — операция, которая не связана с Git напрямую и выполняется через графический интерфейс GitHub (кнопка Fork в правом верхнем углу страницы репозитория). «Форк» создаёт независимую копию репозитория со всеми файлами, коммитами и ветками в аккаунте GitHub. Такая копия будет полностью независима. Внесённые изменения не будут синхронизированы с исходным репозиторием.**
**💡 Комбинацию «форк» + clone часто используют для внесения изменений в публичные репозитории. В этом случае «форк» становится подготовительным этапом перед клонированием чужого репозитория на локальный компьютер.
**Если репозиторий приватный или это репозиторий вашей компании, при работе с ним достаточно clone.**
2. SSH-ключи
* Протокол SSH обеспечивает безопасный обмен данными в сети. С его помощью можно получать данные с удалённого компьютера или отправлять их на него. Трафик шифруется, поэтому протокол безопасен.
* SSH-ключ состоит из двух частей — публичной и приватной. Приватный ключ хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных. Публичный ключ доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.
* Файл с расширением .pub содержит публичный ключ, им можно делиться с веб-сайтами или коллегами. Файл без расширения .pub — приватный.
* Прежде чем генерировать новую пару ключей, следует убедиться, что они отсутствуют на вашем компьютере. Проверить это можно командой ls -la .ssh/ в домашней директории. Если ключи отсутствуют, создать их можно командой ssh-keygen в директории ~/.ssh. После генерации ключ нужно привязать к GitHub.