
## Задание 1 - Автоматизация проверки формата файлов при коммите
Создание скрипта для проверки файлов
Настройка Git Hooks
Добавление скрипта в хук
  <img width="1470" alt="Снимок экрана 2024-12-12 в 19 10 18" src="https://github.com/user-attachments/assets/db9ea3e8-267e-4cd9-ae42-22605a84201d" />

<img width="1470" alt="Снимок экрана 2024-12-12 в 19 10 59" src="https://github.com/user-attachments/assets/161c1a52-1ff3-42dd-8c6f-be9ce42f0edc" />

<img width="1470" alt="Снимок экрана 2024-12-12 в 19 22 11" src="https://github.com/user-attachments/assets/10898cb5-1125-44e6-bd43-4204e87fef61" />

Теперь каждый .txt файл, добавляемый в коммит, будет автоматически проверяться на наличие строки Author: в конце. Если файл не соответствует требованиям, коммит будет заблокирован.
## Задание 2 - Использование Git Flow в проекте
 
Предположим, у вас есть задача на создание новой функциональности для вашего проекта с использованием Git Flow. Давайте рассмотрим конкретный пример. В примере важен не сам проект и его код (его тут вообще как такового нет), а принцип работы Git Flow.

1. Убедитесь, что Git Flow установлен на локальной машине:
<img width="1470" alt="Снимок экрана 2024-12-12 в 19 25 04" src="https://github.com/user-attachments/assets/8efebf52-14e6-4765-bf22-de0f2ddf3cf5" />

<img width="1470" alt="Снимок экрана 2024-12-12 в 19 25 19" src="https://github.com/user-attachments/assets/c94380a6-4559-4344-8642-5a3a67202d14" />

2. В корне репозитория выполните инициализацию Git Flow.

```
git flow init
```

3. Создайте ветку для новой функциональности, допустим она называется "task-management":

<img width="1470" alt="Снимок экрана 2024-12-13 в 00 00 24" src="https://github.com/user-attachments/assets/02d825b9-614f-430f-9cd0-8ed98953cf3f" />

```
git flow feature start task-management
```

<img width="1470" alt="Снимок экрана 2024-12-13 в 00 00 58" src="https://github.com/user-attachments/assets/d4d4728a-d458-4653-9443-140a2b4ba150" />

![image](https://github.com/user-attachments/assets/6cde0bdf-6741-46c7-bb77-87ac51cf6d82)

4. Внесите изменения в код для добавления функционала управления задачами (например, в файл task_manager.py):
![image](https://github.com/user-attachments/assets/38f44900-2974-428c-9f21-28ab0c205531)

```
def create_task(title, description):
    # Логика создания задачи
    print(f"Создана новая задача: {title}")
```

Выполните коммит изменения по мере разработки:

```
git add task_manager.py
git commit -m "Добавлен функционал управления задачами"


```

5. После завершения разработки функции завершите фичу и объедините ее с основной веткой:

```
git flow feature finish task-management

```

Git Flow автоматически переключится на ветку develop и выполнит слияние. Если есть конфликты, их нужно разрешить.

6. Переключитесь на ветку "develop" и начните создание релиза:

```
git checkout develop
git flow release start v1.0.0
```

7. Внесите изменения, связанные с релизом (например, обновите версию в файле version.txt):

```
echo "v1.0.0" > version.txt
git add version.txt
git commit -m "Обновлена версия для релиза v1.0.0"

```

8. Завершите релиз и объедините его с ветками "develop" и "main":

```
git flow release finish v1.0.0
```

9. Если в процессе использования выявлена критическая ошибка, создайте hotfix (у нас конечно же ошибки никакой не возникнет, но hotfix все равно создаем):

```
git flow hotfix start hotfix-1.0.1
```

10. Внесите изменения для исправления ошибки и коммитите:

```
# Исправление ошибки
git add file_with_error.py
git commit -m "Исправлена критическая ошибка"
```

11. Завершите hotfix и объедините его с ветками "develop" и "main":

```
git flow hotfix finish hotfix-1.0.1
```

12. Завершение работы и отправка изменений на удаленный репозиторий. Отправьте изменения на удаленный репозиторий:

```
git push origin develop
git push origin main

```
### Как успешно сдать работу?

Создать свой репозиторий из шаблона этого. Как это делается - "Use this template" -> "Create a new repository" и сделайте его public. 

Находясь уже в своем репозитории - создайте новый файл формата .md и там оформляйте отчет. В отчете опишите все шаги которые вы делали, чтобы получить финальный результат работы.

Что вам нужно знать, чтобы успешно защитить работу:

Основные команды Git, как возникают и как решать конфликты, Git Hooks, Git Flow. 

## Ресурсы

1. [Git Documentation](https://git-scm.com/doc)
2. [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)
3. [Pro Git Book](https://git-scm.com/book/en/v2)
4. [Markdown Guidelines](https://docs.github.com/ru/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
