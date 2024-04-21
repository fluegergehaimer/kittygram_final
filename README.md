![example workflow](https://github.com/github/docs/actions/workflows/main.yml/badge.svg)


# [![Typing SVG](https://readme-typing-svg.herokuapp.com?color=%2336BCF7&lines=KITTYGRAM)](https://git.io/typing-svg)

## Сервис для пользователей, с возможностью поделиться фотографиями и достижениями котов.
### Зарегестрированные пользователи могут выкладывать фотографии своих (и не только) котов с указанием имени, даты рождения и особых заслугах.

## Стек:

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)
![Gunicorn](https://img.shields.io/badge/gunicorn-%298729.svg?style=for-the-badge&logo=gunicorn&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

## Как развернуть проект:
Ссылка на проект: https://github.com/fluegergehaimer/kittygram_final

1.Скопировать <docker-compose.production.yml> из корневой папки проекта

2.Создать и заполнить файл <.env> по примеру <.env.example>

3.Поднять проект:
```
sudo docker compose -f docker-compose.yml up -d
```
4.Выполнить миграции:
```
sudo docker compose -f docker-compose.yml exec backend python manage.py migrate
```
5.Собрать статику:
```
sudo docker compose -f docker-compose.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
```
## Деплой с помощью GitHubActions
1.Клонировать репозиторий

2.Содержимое файла <kittygram_workflow.yml> добавить в <.github/workflow/main.yml>

3.Добавить секреты к репозиторию:
```
DOCKER_PASSWORD - пароль доступа к DockerHub
DOCKER_USERNAME - имя пользователя DockerHub
HOST - ip сервера
POSTGRES_DB - название БД
POSTGRES_PASSWORD - пароль к БД
POSTGRES_USER - имя пользователя БД
SSH_KEY - ключ ssh для доступа к удаленному серверу
SSH_PASSPHRASE - пароль доступа к серверу
TELEGRAM_TO - id telegram
TELEGRAM_TOKEN - token бота
USER - имя пользователя сервера
```
4.При пуше в любую ветку репозитория будут проводиться тесты, при пуше в ветку <main> будет произведен деплой проекта.








Авторы: 
```
- команда Yandex-практикума https://github.com/yandex-praktikum?tab=repositories
```
```
- fluegergehaimer https://github.com/fluegergehaimer
```