## Работа с удалёнными репозиториями

- Открыл и обозвал папку латинницей
- Открыл папку в VSC и сделал **git init**
- Получил в ответ: **Initialized empty Git repository in** D:/Ranis/GB/GB_Learn3/.git/ - вариативно(название диска и папки)
- Далее пошёл на GitHub на аккаунт того чей репозиторий нужен, в правом верхнем углу нажимаем  **Fork.**
- перебрасывает к себе на аккаунт GitHub, внизу нажимаем зелёную кнопку Create fork
- потом зелёную **Code**
- в выпавшем окошке выбираем **HTPPS** и копируем ссылку
- переходим в VSC и набираем **git remote add origin** [https://github.com/Ranis1612/3812_git.git](https://github.com/Ranis1612/3812_git.git) - ссылка из **Code в конце должно быть [.git](https://github.com/Ranis1612/3812_git.git) без всяких цифр, букв и тильд**
- если никакой реакции не последовало то всё ЗБ.
- пишем далее git clone [https://github.com/Ranis1612/3812_git.git](https://github.com/Ranis1612/3812_git.git) - та же ссылка
- и получаем в ответ что то вроде этого:

Cloning into **'3812_git'**...
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (2/2), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 9 (delta 0), reused 0 (delta 0), pack-reused 7
Receiving objects: 100% (9/9), done.

- **проверяем появились ли в указанной папке нужные файлы.**
- **если обнаруживаем ветку (master) и не ту папку что указана в репозитории** то переходим в нужную и создаём новый терминал, после чего должна появиться ветка **(main)** и там уже командуем **git pull**
- для актуализации текущей версии репозитория на GitHub нажимаем **Synk Fork (Вилка синхронизации)**  под кнопкой **Code**
- git remote -v - проверяем адрес удалённого репозитория
- Далее если всё норм создаём новую ветку и в ней новый файл НЕ ЗАБЫВАЕМ УКАЗЫВАТЬ РАСШИРЕНИЕ ФАЙЛА .md , .txt  итд:

git checkout -b version_1

git add version_1Ranis.md - обязательно в первый раз добавляем через add

git commit -m "Создал новый файл version_1Ranis.md”

если всё норм получаем:

[version_1 158aacf] Создал новый файл version_1Ranis.md
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 version_1Ranis.md

- В этом файле уже начинаем работать.
- git push не сработает т.к удалённый репозиторий пока не знает об этой ветке - она не записана, поэтому применяем команду **git push --set-upstream origin version_1**  или **git push -u origin version_1** (название ветки)
- Получаем в ответ о созданном запросе на слияние он же pull request

Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 352 bytes | 352.00 KiB/s, done.
Total 3 (delta 0), reused 1 (delta 0), pack-reused 0
remote:
remote: Create a **pull reques**t for 'version_1' on GitHub by visiting:
remote:      [https://github.com/Ranis1612/3812_git/pull/new/version_1](https://github.com/Ranis1612/3812_git/pull/new/version_1)
remote:
To [https://github.com/Ranis1612/3812_git.git](https://github.com/Ranis1612/3812_git.git)

[new branch] version_1 -> version_1
branch 'version_1' set up to track 'origin/version_1'.

- далее мы можем перейти по ссылке напрямую или перейти в профиль на GitHub и и нажать на Compare & pull request
- Видим commit создаётся, нажимаем create pull request

при этом создаётся pull request это и есть запрос на слияние.