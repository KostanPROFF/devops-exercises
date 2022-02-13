## Git

|Name|Topic|Objective & Instructions|Solution|Comments|
|--------|--------|------|----|----|
| Мой первый коммит | Commit | [Exercise](exercises/git/commit_01.md) | [Solution](exercises/git/solutions/commit_01_solution.md) | | |
| Time to Branch | Branch | [Exercise](exercises/git/branch_01.md) | [Solution](exercises/git/solutions/branch_01_solution.md) | | |
| Squashing Commits | Commit | [Exercise](exercises/git/squashing_commits.md) | [Solution](exercises/git/solutions/squashing_commits.md) | | |

<details>
<summary>Как узнать, является ли определенный каталог репозиторием git? </summary><br><b>

Вы можете проверить, существует ли каталог ".git".
</b></details>

<details>
<summary>Объясните следующее: <code>git directory</code>, <code>working directory</code> и <code>staging area</code></summary><br><b>

Этот ответ взят с сайта [git-scm.com](https://git-scm.com/book/en/v1/Getting-Started-Git-Basics#_the_three_states)

"Каталог Git" - это место, где Git хранит метаданные и базу данных объектов для вашего проекта. Это самая важная часть Git'а, и именно она копируется при клонировании репозитория с другого компьютера.

Рабочий каталог представляет собой один чек-аут одной версии проекта. Эти файлы извлекаются из сжатой базы данных в каталоге Git и помещаются на диск для использования или изменения.

Область постановки - это простой файл, обычно содержащийся в вашей директории Git, в котором хранится информация о том, что войдет в ваш следующий коммит. Иногда его называют индексом, но в последнее время становится стандартным называть его областью постановки".
</b></details>

<details>
<summary>В чем разница между <code>git pull</code> и <code>git fetch</code>? </summary><br><b>

Вкратце, git pull = git fetch + git merge

Когда вы запускаете git pull, он получает все изменения с удаленного или центрального сервера.
репозитория и прикрепляет его к соответствующей ветке в вашем локальном репозитории.

git fetch получает все изменения из удаленного хранилища, сохраняет изменения в
отдельную ветвь в вашем локальном репозитории
</b></details>

<details>
<summary>Как проверить, отслеживается ли файл, и если нет, то отследить его?</summary><br><b>

Существуют различные способы проверки того, отслеживается ли файл или нет:

  - `git ls-file <file>` -> код выхода 0 означает, что он отслежен
  - `git blame <file>`
  ...
</b></details>

<details>
<summary>Как можно увидеть, какие изменения были сделаны до их фиксации?</summary><br><b>

`git diff``.
</b></details>

<details>
<summary>Что делает <code>git status</code>? </summary><br><b>
</b></details>

<details>
<summary>У вас есть две ветки - main и devel. Как убедиться, что devel синхронизируется с main? </summary><br><b>

```
git checkout main
git pull
git checkout devel
git merge main
```
</b></details>

#### Git - Merge

<details>
<summary>У вас есть две ветви - main и devel. Как поместить devel в main? </summary><br><b>

```
git checkout main
git merge devel
git push origin main
```
</b></details>

<details>
<summary>Как разрешить конфликты слияния git? </summary><br><b>

< p>
Сначала вы открываете файлы, которые находятся в конфликте, и определяете, в чем заключается конфликт.
Далее, исходя из того, что принято в вашей компании или команде, вы либо обсуждаете с вашим
коллеги по конфликтам или разрешить их самостоятельно
После разрешения конфликтов вы добавляете файлы с помощью `git add <имя_файла>`.
Наконец, вы запускаете `git rebase --continue`.
</p>
</b></details>

<details>
<summary>С какими стратегиями слияния вы знакомы? </summary><br><b>

Упоминания двух или трех должно быть достаточно, и, вероятно, будет полезно упомянуть, что "рекурсивный" - это тот, который используется по умолчанию.

рекурсивный
решить
наш
их

Эта страница объясняет это лучше всего: https://git-scm.com/docs/merge-strategies
</b></details>

<details>
<summary>Объяснение Git octopus merge</summary><br><b>

Наверное, хорошо бы упомянуть, что это:

  * Это хорошо для случаев слияния более чем одной ветки (а также по умолчанию для таких случаев)
  * В основном он предназначен для объединения ветвей тем вместе

Это отличная статья о слиянии осьминогов: http://www.freblogg.com/2016/12/git-octopus-merge.html.
</b></details>

<details>
<summary>В чем разница между <code>git reset</code> и <code>git revert</code>? </summary><br><b>

< p>

`git revert` создает новый коммит, который отменяет изменения последнего коммита.

`git reset` зависит от использования, может изменить индекс или изменить коммит, который возглавляет ветвь.
в настоящее время указывает на.
</p>
</b></details>

#### Git - Rebase

<details>
<summary>Вы хотели бы продвинуться вперед и занять первое место. Как бы вы этого добились? </summary><br><b>

Использование команды `git rebase`
</b></details>

<details>
<summary>В каких ситуациях вы используете <code>git rebase</code>? </summary><br><b>
</b></details>

<details>
<summary>Как вернуть определенный файл к предыдущему коммиту?</summary><br><b>

```
git checkout HEAD~1 -- /path/of/the/file
```
</b></details>

<details>
<summary>Как сжать два последних коммита?</summary><br><b>
</b></details>

<details>
<summary>Что такое каталог <code>.git</code>? Что вы можете там найти? </summary><br><b>
  В папке   <code>.git</code> содержится вся информация, необходимая для работы вашего проекта в системе контроля версий, а также вся информация о коммитах, адресе удаленного репозитория и т. д. Все они присутствуют в этой папке. Она также содержит журнал, в котором хранится история коммитов, чтобы вы могли откатиться к истории.


Эта информация скопирована с [https://stackoverflow.com/questions/29217859/what-is-the-git-folder](https://stackoverflow.com/questions/29217859/what-is-the-git-folder)
</b></details>

<details>
<summary>Каковы некоторые анти-паттерны Git? Вещи, которые не следует делать</summary><br><b>

  * Не ждать слишком долго между коммитами
  * Не удалять каталог .git :)
</b></details>

<details>
<summary>Как удалить удаленную ветку?</summary><br><b>

Вы удаляете удаленную ветвь с помощью этого синтаксиса:

git push origin :[имя_ветви]
</b></details>

<details>
<summary>Знакомы ли вы с gitattributes? Когда вы будете его использовать? </summary><br><b>

gitattributes позволяет определять атрибуты для каждого имени пути или шаблона пути.< br>

Вы можете использовать его, например, для контроля конечных строк в файлах. В системах на базе Windows и Unix для новых строк используются разные символы (\r\n и \n соответственно). Поэтому, используя gitattributes, мы можем выровнять их для Windows и Unix с помощью `* text=auto` в .gitattributes для всех, кто работает с git. Таким образом, если вы используете Git-проект в Windows, вы получите \r\n, а если в Unix или Linux, то \n.
</b></details>

<details>
<summary>Как отменить изменения локальных файлов? (до фиксации)</summary><br><b>

`git checkout -- <имя_файла>`
</b></details>

<details>
<summary>Как отбрасывать локальные коммиты?</summary><br><b>

`git reset HEAD~1` для удаления последнего коммита
Если вы хотите также отменить изменения, вы `git reset --hard``.
</b></details>

<details>
<summary> Правда или ложь? Чтобы удалить файл из git, но не из файловой системы, нужно использовать <code>git rm </code></summary><br><b>

Ложь. Если вы хотите сохранить файл в вашей файловой системе, используйте `git reset <имя_файла>`.
</b></details>
