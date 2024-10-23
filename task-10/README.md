# Задание №10

## Веб-приложение

### Задача

Напишите веб-приложение для получения информации о пользователях и их постах.
Реализуйте разные уровни доступа.
Для проверки аутентификации обращайтесь к микросервису, который вы написали ранее.

### Описание

Предварительно наполните базу данных сущностями user, user-address, post.
Используйте навыки, полученные в практической работе №8.

Разработайте микросервис на FastAPI и SQLAlchemy asyncio, который будет отдавать информацию по пользователям и постам.

Отдавайте ограниченные данные анонимным пользователям,
отдавать более полные данные аутентифицированным пользователям,
отдавайте полную информацию о себе текущему пользователю: включая email и адрес проживания.

Для проверки авторизации обращайтесь к микросервису, который вы написали в практической работе №9.

Реализуйте следующие представления:

- получение списка пользователей;
- получение деталей пользователя по идентификатору;
- получение расширенных деталей текущего пользователя по токену;
- получение списка постов;
- получение деталей поста по идентификатору;
- получение списка постов для выбранного пользователя (по идентификатору пользователя).


#### Валидация токена

Учтите, что токен может быть не передан, и большинство представлений это позволяют.

Если токен передан, то он должен быть валидным. Если токен невалиден, выкидывайте исключение.

#### Стыковка данных

В вашем приложении будут данные, которые вы получили по API и сложили в базу данных.

Для получения информации о текущем пользователе будет необходимо сопоставлять информацию,
которая возвращается из сервиса аутентификации, с тем, что лежит у вас в базе данных.

Решите, как вы будете искать пользователя в базе. Например, можно стыковать по юзернейму, или почте.

Это точно не должен быть primary key id, так как в каждом сервисе айди будет свой.

#### Уровни доступа к данным

Если запрос выполняет анонимный пользователь, отдавайте минимум информации по пользователю, например айди и имя.

Если запрос отправлен аутентифицированным пользователем, отдавайте больше информации, чем для анонимов.
Например, добавьте в ответ ещё и username.

#### Список пользователей

Представление для получения списка всех пользователей.

#### Детали пользователя

Представление для получения деталей пользователя по айди.

Если по переданному айди пользователь не найден, возвращайте ошибку not found.

#### Информация о себе

Представление должно возвращать детальную информацию по запрашивающему пользователю.

Если данные по пользователю есть в сервисе, верните полную информацию: детали пользователя, адрес проживания.

#### Список постов

Представление для получения списка всех постов.

#### Детали поста

Представление для получения деталей поста по айди.

Если пост по айди не найден, возвращайте ошибку not found.

#### Список постов пользователя

Представление для получения списка всех постов для указанного пользователя.
Принимайте айди пользователя в пути запроса.