# Система Контроля Успеваемости Обучающихся

Данная система предназначена для автоматизации процессов управления учебными курсами, выставления оценок и отслеживания успеваемости студентов. В системе реализованы три ключевые роли: студент, преподаватель и администратор.

---

## Структура функциональных возможностей (Mind Map)

```mermaid
mindmap
  root((Система контроля успеваемости))
    Авторизация и регистрация
      Регистрация пользователя
      Авторизация пользователя
    Курсы
      Просмотр курсов студентом
      Управление курсами администратором
        Добавление нового курса
        Прикрепление студентов к курсу
        Прикрепление преподавателей к курсу
    Оценки
      Выставление оценок преподавателем
      Просмотр оценок студентом
      Уведомления
        Уведомление студентов о новых оценках
```

### Описание диаграммы
- **Корень:** Основной функционал системы контроля успеваемости.
- **Авторизация и регистрация:** Позволяет пользователям зарегистрироваться в системе и авторизоваться.
- **Курсы:** Управление курсами включает:
  - Просмотр курсов студентами.
  - Добавление новых курсов, прикрепление студентов и преподавателей администратором.
- **Оценки:** Преподаватели выставляют оценки, а студенты их просматривают. Система отправляет уведомления студентам о новых оценках.

---
 
 ---

## Диаграмма путешествия пользователя (User Journey Diagram)

```mermaid
%%{init: {"themeVariables": {"journeySectionFontSize": "10px", "journeyFontSize": "12px", "journeyMargin": "20px"}}}%%
journey
  title Путешествие пользователя
  section Регистрация
    Пользователь: 5: Ввод данных
    Система: 4: Проверка данных
    Пользователь: 5: Получает доступ
  section Функционал
    Студент: 5: Просматривает курсы и оценки
    Преподаватель: 4: Выставляет оценки
    Администратор: 5: Управляет курсами
    Администратор: 5: Прикрепляет студента к курсу
  section Уведомления
    Система: 5: Посылает уведомления
    Студент: 4: Получает уведомления

```
### Описание диаграммы
1. **Регистрация и авторизация:** Пользователь регистрируется или входит в систему через форму авторизации.
2. **Использование функционала:**
   - Студент может просматривать свои курсы и оценки.
   - Преподаватель выставляет оценки студентам.
   - Администратор управляет курсами, добавляя новые или редактируя существующие.
3. **Уведомления:** Студент получает уведомления от системы о выставленных оценках.

---

## Квадрант-граф (Priority Matrix)

```mermaid
pie
    "Авторизация и регистрация" : 40
    "Управление курсами администратором" : 40
    "Просмотр оценок студентом" : 20
    "Выставление оценок преподавателем" : 20
    "Уведомления студентов" : 10
    "Расширенные аналитические отчеты" : 10
```
### Описание диаграммы
- **Квадрант 1 (Высокая ценность, Высокая сложность):**
  - Уведомления для студентов о новых оценках.
  - Полное управление курсами со стороны администратора.
- **Квадрант 2 (Высокая ценность, Низкая сложность):**
  - Просмотр оценок студентом.
  - Выставление оценок преподавателем.
- **Квадрант 3 (Низкая ценность, Низкая сложность):**
  - Основной функционал регистрации и авторизации пользователей.
- **Квадрант 4 (Низкая ценность, Высокая сложность):**
  - Расширенные аналитические отчеты для пользователей системы.

---
## Git Graph

```mermaid
gitGraph
    commit id: "Инициализация проекта"
    branch develop
    checkout develop
    commit id: "Реализация авторизации и регистрации"
    branch feature/courses
    checkout feature/courses
    commit id: "Реализация функционала управления курсами"
    checkout develop
    merge feature/courses
    branch feature/grades
    checkout feature/grades
    commit id: "Добавление выставления оценок"
    checkout develop
    merge feature/grades
    branch feature/notifications
    checkout feature/notifications
    commit id: "Уведомления студентов"
    checkout develop
    merge feature/notifications
    commit id: "Подготовка к релизу"
```
### Описание графа
- **Инициализация проекта:** Создание базовой структуры проекта.
- **Разработка:** Ветка `develop` служит для объединения всех фич.
- **Реализация функционала:**
  - `feature/courses`: Добавление и управление курсами.
  - `feature/grades`: Возможность выставлять оценки.
  - `feature/notifications`: Уведомления для студентов.
- **Слияние и релиз:** Все фичи объединены в ветку `develop`, после чего проект готовится к релизу.


