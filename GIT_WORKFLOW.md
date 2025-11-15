# Git Workflow для roadmap

## Для ментора (ты)

### Первая настройка репозитория
```bash
cd roadmap
git init
git add .
git commit -m "Initial roadmap structure"
git branch -M main
git remote add origin https://github.com/savinmikhail/roadmap.git
git push -u origin main
```

### Обновление roadmap
Когда добавляешь новые материалы или исправляешь что-то:
```bash
git add .
git commit -m "Update: добавил новый этап / исправил ссылку"
git push
```

---

## Для студентов

### Вариант 1: Fork (рекомендуется)
Студент получает свою копию и может синхронизироваться с обновлениями.

**Шаг 1: Fork репозитория**
1. Зайди на https://github.com/savinmikhail/roadmap
2. Нажми кнопку "Fork" вверху справа
3. Теперь у тебя есть своя копия!

**Шаг 2: Клонируй свой fork**
```bash
git clone https://github.com/ТвойUsername/roadmap.git
cd roadmap
```

**Шаг 3: Добавь upstream (связь с оригиналом)**
```bash
git remote add upstream https://github.com/savinmikhail/roadmap.git
```

**Шаг 4: Работай и сохраняй прогресс**
```bash
# После того как выполнил задачи
git add .
git commit -m "Progress: completed stage 1.3"
git push origin main
```

**Шаг 5: Получай обновления от ментора**
Когда ментор обновил roadmap:
```bash
git fetch upstream
git merge upstream/main
# Или если хочешь перезаписать свои изменения:
# git reset --hard upstream/main
```

---

### Вариант 2: Template (проще, но без синхронизации)
Если не хочешь возиться с Git.

**В GitHub**:
1. Зайди на https://github.com/savinmikhail/roadmap
2. Нажми "Use this template" → "Create a new repository"
3. Назови свой репо (например, "my-roadmap")
4. Clone и работай

**Минус**: не получится автоматически подтягивать обновления от ментора.

---

### Вариант 3: Просто скачать ZIP
Самый простой, но совсем без Git.

1. Скачай ZIP с GitHub
2. Распакуй
3. Работай локально
4. Делай бэкапы вручную

---

## Как ментор может отслеживать прогресс студентов

### Вариант A: Студенты форкают
- Смотришь их репозитории на GitHub
- Видишь коммиты и изменения
- Можешь оставлять комментарии через Issues/PR

### Вариант B: Shared workspace
- Создаешь приватный репо для каждого студента
- Даешь ему доступ
- Ты можешь push'ить обновления, он может pull'ить

### Вариант C: GitHub Projects
- Создаешь GitHub Projects board
- Каждый студент = колонка или отдельный issue
- Отслеживаешь всех на одной доске

---

## Полезные команды

```bash
# Посмотреть статус
git status

# Посмотреть историю
git log --oneline

# Откатить последний коммит (но оставить изменения)
git reset --soft HEAD~1

# Посмотреть что изменилось
git diff

# Создать ветку для эксперимента
git checkout -b experiment

# Вернуться на main
git checkout main
```

---

## Troubleshooting

**Проблема**: Конфликты при merge
**Решение**: Открой файлы с конфликтами, вручную выбери что оставить, потом:
```bash
git add .
git commit -m "Resolved merge conflicts"
```

**Проблема**: Случайно закоммитил лишнее
**Решение**: 
```bash
git reset --soft HEAD~1  # откатить коммит
git reset HEAD file.txt  # убрать файл из stage
```

**Проблема**: Хочу начать с чистого листа
**Решение**: Удали папку, клонируй заново
```bash
cd ..
rm -rf roadmap
git clone [url]
```
