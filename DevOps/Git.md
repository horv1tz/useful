# Git

Git — это распределенная система управления версиями, которая позволяет отслеживать изменения в коде и работать совместно с другими разработчиками.

## Настройка Git

Перед началом работы необходимо настроить Git с помощью следующих команд:

- **Установка имени пользователя:**
  ```bash
  git config --global user.name "Ваше имя"
  ```
  Это имя будет отображаться в информации о коммитах.

- **Установка электронной почты:**
  ```bash
  git config --global user.email "email@example.com"
  ```
  Email также будет отображаться в коммитах.

- **Проверка текущих настроек:**
  ```bash
  git config --list
  ```
  Показывает все текущие настройки Git.

- **Настройка предпочтительного редактора:**
  ```bash
  git config --global core.editor "vim"
  ```
  Устанавливает редактор по умолчанию для Git.

- **Выбор отображения цветов:**
  ```bash
  git config --global color.ui auto
  ```
  Включает цветное отображение в командной строке.

## Создание и Клонирование Репозитория

- **Инициализация нового репозитория:**
  ```bash
  git init
  ```
  Создает новый локальный репозиторий в текущей директории.

- **Клонирование существующего репозитория:**
  ```bash
  git clone <URL>
  ```
  Клонирует удаленный репозиторий в новую директорию.

  **Пример:**
  ```bash
  git clone https://github.com/user/repo.git
  ```

## Основные Команды

### Статус и Добавление Файлов

- **Проверка статуса репозитория:**
  ```bash
  git status
  ```
  Показывает отслеживаемые и неотслеживаемые файлы, изменения и статус индекса.

- **Добавление файлов в индекс:**
  ```bash
  git add <файл>
  ```
  Добавляет указанный файл в индекс (staging area).

  **Добавление всех файлов:**
  ```bash
  git add .
  ```
  Добавляет все новые и измененные файлы в индекс.

### Коммит изменений

- **Создание коммита:**
  ```bash
  git commit -m "Сообщение коммита"
  ```
  Фиксирует изменения с указанным сообщением.

- **Автоматическое добавление и коммит:**
  ```bash
  git commit -a -m "Сообщение коммита"
  ```
  Добавляет изменения отслеживаемых файлов и создает коммит.

### Работа с Удаленными Репозиториями

- **Отправка изменений:**
  ```bash
  git push
  ```
  Отправляет коммиты в удаленный репозиторий по умолчанию.

  **Отправка на определенную ветку:**
  ```bash
  git push origin <ветка>
  ```

- **Получение изменений:**
  ```bash
  git pull
  ```
  Забирает изменения из удаленного репозитория и сливает их с текущей веткой.

  **Разница между `git fetch` и `git pull`:**

  - `git fetch` загружает изменения из удаленного репозитория, но не сливает их.
  - `git pull` сочетает `git fetch` и `git merge`.

## Работа с Ветками

- **Просмотр локальных веток:**
  ```bash
  git branch
  ```
  Выводит список всех локальных веток.

- **Создание новой ветки:**
  ```bash
  git branch <название_ветки>
  ```
  Создает новую ветку.

- **Переключение между ветками:**
  ```bash
  git checkout <название_ветки>
  ```
  Переключается на указанную ветку.

- **Создание и переключение на новую ветку:**
  ```bash
  git checkout -b <название_ветки>
  ```
  Создает новую ветку и сразу переключается на нее.

- **Слияние веток:**
  ```bash
  git merge <название_ветки>
  ```
  Сливает указанную ветку с текущей.

- **Удаление ветки:**
  ```bash
  git branch -d <название_ветки>
  ```
  Удаляет локальную ветку. Если ветка не была слита, используйте принудительное удаление:
  ```bash
  git branch -D <название_ветки>
  ```

### Работа с Удаленными Ветками

- **Просмотр удаленных веток:**
  ```bash
  git branch -r
  ```

- **Удаление удаленной ветки:**
  ```bash
  git push origin --delete <название_ветки>
  ```

- **Получение всех веток и тегов:**
  ```bash
  git fetch --all
  ```

## Просмотр Истории

- **Полная история коммитов:**
  ```bash
  git log
  ```
  Показывает историю коммитов с деталями.

- **Краткий формат истории:**
  ```bash
  git log --oneline
  ```
  Отображает историю в одну строку на коммит.

- **Графическое отображение:**
  ```bash
  git log --graph --all --decorate --oneline
  ```
  Показывает историю в виде графа, отображая ветки и коммиты.

- **Фильтрация по автору:**
  ```bash
  git log --author="Имя"
  ```

- **Поиск по сообщению коммита:**
  ```bash
  git log --grep="Текст поиска"
  ```

## Сравнение Изменений

- **Просмотр изменений в рабочем каталоге:**
  ```bash
  git diff
  ```
  Показывает изменения, которые еще не добавлены в индекс.

- **Просмотр изменений в индексе:**
  ```bash
  git diff --staged
  ```
  Показывает изменения, подготовленные для коммита.

- **Сравнение между двумя ветками:**
  ```bash
  git diff <ветка1> <ветка2>
  ```

## Отмена Изменений

- **Отмена изменений в файле:**
  ```bash
  git checkout -- <файл>
  ```
  Возвращает файл к последнему коммиту, отменяя несохраненные изменения.

- **Убрать файл из индекса:**
  ```bash
  git reset HEAD <файл>
  ```
  Убирает файл из индекса, оставляя его изменения в рабочем каталоге.

- **Отмена последнего коммита (с сохранением изменений):**
  ```bash
  git reset --soft HEAD~1
  ```
  Сбрасывает коммит, оставляя изменения в индексе.

- **Отмена последнего коммита (с удалением изменений):**
  ```bash
  git reset --hard HEAD~1
  ```
  Полностью удаляет последний коммит и все изменения.

- **Создание обратного коммита:**
  ```bash
  git revert <хеш_коммита>
  ```
  Создает новый коммит, отменяющий указанный коммит.

## Работа с Удаленными Репозиториями

- **Просмотр удаленных репозиториев:**
  ```bash
  git remote -v
  ```
  Показывает имена и URL удаленных репозиториев.

- **Добавление удаленного репозитория:**
  ```bash
  git remote add origin <URL>
  ```
  Добавляет удаленный репозиторий с именем `origin`.

- **Переименование удаленного репозитория:**
  ```bash
  git remote rename <старое_имя> <новое_имя>
  ```

- **Удаление удаленного репозитория:**
  ```bash
  git remote remove <имя>
  ```

## Теги

- **Просмотр тегов:**
  ```bash
  git tag
  ```
  Показывает список всех тегов.

- **Создание аннотированного тега:**
  ```bash
  git tag -a v1.0 -m "Версия 1.0"
  ```

- **Создание легковесного тега:**
  ```bash
  git tag v1.0
  ```

- **Просмотр информации о теге:**
  ```bash
  git show v1.0
  ```

- **Отправка тегов в удаленный репозиторий:**
  ```bash
  git push origin v1.0
  ```
  Отправляет указанный тег.

  **Отправка всех тегов:**
  ```bash
  git push origin --tags
  ```

- **Удаление тега локально:**
  ```bash
  git tag -d v1.0
  ```

- **Удаление тега в удаленном репозитории:**
  ```bash
  git push origin :refs/tags/v1.0
  ```

## Сохранение Изменений (Stash)

- **Сохранение незаконченных изменений:**
  ```bash
  git stash
  ```
  Сохраняет текущие изменения и очищает рабочий каталог.

- **Просмотр сохраненных изменений:**
  ```bash
  git stash list
  ```

- **Применение последних сохраненных изменений:**
  ```bash
  git stash apply
  ```

- **Применение и удаление из списка:**
  ```bash
  git stash pop
  ```

- **Удаление сохраненных изменений:**
  ```bash
  git stash drop
  ```

- **Сохранение с сообщением:**
  ```bash
  git stash save "Описание"
  ```

- **Применение конкретного stash:**
  ```bash
  git stash apply stash@{2}
  ```

## Работа с Submodules (Подмодулями)

- **Добавление подмодуля:**
  ```bash
  git submodule add <URL> <путь>
  ```

- **Инициализация и обновление подмодулей:**
  ```bash
  git submodule update --init --recursive
  ```

- **Обновление подмодулей до последних версий:**
  ```bash
  git submodule update --remote
  ```

- **Удаление подмодуля:**
  ```bash
  git submodule deinit -f <путь_к_подмодулю>
  rm -rf .git/modules/<путь_к_подмодулю>
  git rm -f <путь_к_подмодулю>
  ```

## Ребейз (Rebase)

- **Перебазирование текущей ветки на другую:**
  ```bash
  git rebase <ветка>
  ```

- **Применение интерактивного ребейза:**
  ```bash
  git rebase -i HEAD~3
  ```
  Позволяет изменить последние три коммита (объединить, изменить сообщения и т.д.).

- **Отмена ребейза:**
  ```bash
  git rebase --abort
  ```

- **Продолжение ребейза после разрешения конфликтов:**
  ```bash
  git rebase --continue
  ```

## Инструменты для Решения Конфликтов

- **Показать файлы с конфликтами:**
  ```bash
  git diff --name-only --diff-filter=U
  ```

- **Отметить конфликт как разрешенный:**
  ```bash
  git add <файл>
  ```

- **Продолжить процесс после разрешения конфликтов:**
  ```bash
  git merge --continue
  ```
  или
  ```bash
  git rebase --continue
  ```

## Дополнительные Полезные Команды

- **Просмотр автора изменений в файле:**
  ```bash
  git blame <файл>
  ```
  Показывает, кто и когда изменял каждую строку в файле.

- **Просмотр содержимого конкретного коммита:**
  ```bash
  git show <хеш_коммита>
  ```

- **Удаление файла из репозитория и файловой системы:**
  ```bash
  git rm <файл>
  ```

- **Переименование или перемещение файла:**
  ```bash
  git mv <старое_имя> <новое_имя>
  ```

- **Очистка неотслеживаемых файлов:**
  ```bash
  git clean -f
  ```
  Удаляет неотслеживаемые файлы из рабочей директории.

  **Удаление неотслеживаемых директорий:**
  ```bash
  git clean -fd
  ```

- **Поиск по истории коммитов:**
  ```bash
  git log -S "фрагмент_кода"
  ```
  Показывает коммиты, в которых добавлен или удален указанный фрагмент кода.

- **Изменение последнего коммита:**
  ```bash
  git commit --amend
  ```
  Позволяет изменить сообщение последнего коммита или добавить забытые изменения.

## Алиасы (Псевдонимы)

Вы можете создать собственные алиасы для часто используемых команд:

- **Создание алиаса:**
  ```bash
  git config --global alias.co checkout
  ```

  Теперь вы можете использовать `git co` вместо `git checkout`.

- **Пример полезных алиасов:**

  ```bash
  git config --global alias.st status
  git config --global alias.br branch
  git config --global alias.cm commit
  git config --global alias.df diff
  git config --global alias.lg "log --graph --oneline --all --decorate"
  ```

## Настройка .gitignore

Файл `.gitignore` используется для указания файлов и директорий, которые Git должен игнорировать.

**Пример содержимого .gitignore:**

```
# Игнорировать все файлы с расширением .log
*.log

# Игнорировать директорию build/
build/

# Игнорировать файл secrets.txt
secrets.txt
```

## Получение Справки

- **Общая справка:**
  ```bash
  git help
  ```

- **Справка по конкретной команде:**
  ```bash
  git help <команда>
  ```
  или
  ```bash
  git <команда> --help
  ```

## Полезные Практики

- **Регулярно коммитьте небольшие изменения.**
- **Используйте понятные сообщения коммитов.**
- **Старайтесь избегать работы в ветке `master` или `main`.**
- **Периодически синхронизируйтесь с удаленным репозиторием.**
- **Перед слиянием обновите свою ветку:**
  ```bash
  git fetch origin
  git merge origin/main
  ```
- **Разрешайте конфликты сразу после их возникновения.**

---

Это подробная шпаргалка по Git, которая поможет вам в повседневной работе с системой контроля версий. Практикуйтесь и изучайте документацию для более глубокого понимания возможностей Git.
