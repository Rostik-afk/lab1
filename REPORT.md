# Лабораторна робота з Git — Звіт

**Студент:** Бойчук Ростислав
**Email:** 022320@university.kherson.ua
**Репозиторій GitHub:** https://github.com/Rostik-afk/lab1

---

## Частина 1. Базова робота з Git

- Встановлено Git `2.54.0.windows.1`.
- Налаштовано identity: `user.name`, `user.email`, `color.ui=auto`, `init.defaultbranch=main`.
- Створено папку `lab1`, виконано `git init`.
- Створено `index.html`, додано в Index (`git add`), зроблено перший коміт.
- Файл змінено, переглянуто `git diff`, зроблено другий коміт.

## Частина 2. Робота з гілками (Branching & Merging)

- Створено гілку `dev` (від `main`).
- Від `dev` створено `feature/login-form`.
- Створено `login.html` у 3 комітах (скелет сторінки → форма входу → стилі).
- Повернутося у `dev`, виконано `git merge --no-ff feature/login-form`.
- Гілку `feature/login-form` видалено.

## Частина 3. Вирішення конфлікту (Conflict Resolution)

- У `main` створено `style.css` з `background: white`.
- У гілці `feature/dark` змінено на `background: black`, закомічено.
- Повернутося у `main`, змінено на `background: blue`, закомічено.
- `git merge feature/dark` → **CONFLICT in style.css**.
- Конфлікт вирішено **комбінуванням обох варіантів**:

```css
body {
    background: linear-gradient(135deg, blue, black);
}
```

- Merge завершено комітом.

---

## Граф історії (критерій прийому)

```
*   057eb87 (HEAD -> main, origin/main) Merge feature/dark into main: resolve conflict
|\  
| * 8e6196a (feature/dark) Change background to black (dark theme)
* | ef8bea7 Change background to blue
|/  
* dc0c93f Add style.css with white background
| * e22aa68 (origin/dev, dev) Merge feature/login-form into dev
|/| 
| * edf7b04 Style login form with basic CSS
| * 77e03f9 Add login form: username and password fields
| * 41098be Add login page skeleton
|/  
* b348e85 Update index.html: add lab description
* 345ad05 Initial commit: add index.html
```

Повний вивід команд — у папці `report/` (`01-git-log.txt`, `02-git-graph.txt`, `03-branches.txt`).
