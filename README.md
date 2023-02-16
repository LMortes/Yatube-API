# Проект «API для Yatube».

## Описание

API для Yatube представляет собой проект социальной сети в которой реализованы следующие возможности:

- публиковать записи 
- комментировать записи
- подписываться или отписываться от авторов.

## Как запустить проект

- Клонируем репозиторий и переходим в папку с проектом
```bash
git clone https://github.com/LMortes/api_final_yatube.git
cd api_final_yatube
```

- Устанавливаем виртуальное окружение
```bash
python -m venv venv
```
- Активируем виртуальное окружение
```bash
source venv/Scripts/activate
```
- Обновляем пакетный менеджер pip
```bash
python -m pip install --upgrade pip
```
- Устанавливаем зависимости из файла requirements.txt

```bash
pip install -r requirements.txt
```
- Выполняем миграции:

```bash
python manage.py makemigrations
python manage.py migrate
```
- Запускаем проект:

```bash
python manage.py runserver
```

## Примеры работы с API для всех пользователей
Неавторизованные пользователи могут лишь добывать информацию. Создать, изменить, удалить что-либо не получится.
```r
GET api/v1/posts/ - получить список всех публикаций.
При указании параметров limit и offset выдача должна работать с пагинацией
GET api/v1/posts/{id}/ - получение публикации по id
GET api/v1/groups/ - получение списка доступных сообществ
GET api/v1/groups/{id}/ - получение информации о сообществе по id
GET api/v1/{post_id}/comments/ - получение всех комментариев к публикации
GET api/v1/{post_id}/comments/{id}/ - Получение комментария к публикации по id
```

## Примеры работы с API для авторизованных пользователей

- Создать публикацию:

```r
POST /api/v1/posts/
```

Тело запроса:

```json
{
"text": "string",
"image": "string",
"group": 0
}
```

- Обновление публикации:

```r
PUT /api/v1/posts/{id}/
```

Тело запроса:

```json
{
"text": "string",
"image": "string",
"group": 0
}
```

- Обновление публикации:

```r
PATCH /api/v1/posts/{id}/
```

Тело запроса:

```json
{
"text": "string",
"image": "string",
"group": 0
}
```

- Удаление публикации:

```r
DEL /api/v1/posts/{id}/
```
