## Basics
### Headers
Заголовки ответа хранятся в похожем на `Map` объекте `response.headers`.  
Можно уст. заголовки запроса использую опцию `headers`. Оно содержит объект с исходящими заголовками.  
Интерфейс Headers позволяет вам создать ваш собственный объект заголовков через конструктор Headers().
### Cookie
Это небольшие строки данных, кот. хранятся в браузере. Они явл. частью HTTP-протокола. Обычно уст. веб-сервером при помощи заголовка Set-Cookie. Затем бразуер будет их авто. добавлять почти в каждый запрос, при помощи заголовка Cookie.  
Нет способа сделать куки доступным на другом домене 2-го уровня.
`document.cookie` - предоставляет доступ к куки
- операция записи кук изменяет только те куки, кот. были указаны
- куки следует передавать только по HTTPS-протоколу

Настройки:
- `path/`, по умолчанию уст. текущий путь, делает куки видимыми по указанному пути и ниже
- `domain=site.com` по умолч. куки видны только на текущем домене, если явно указан домен, то куки станут видны и на поддоменах
- `expires`, `max-age` уст. дату истечения, без них куки умерт при закрытии браузера
- `secure` делает куки доступными только при исп. https
- `samesite` предотвращает XSRF-атаки

### OAUTH
Это схема авторизации, позволяющая предоставить третьей стороне ограниченный доступ к ресурсам пользователя, без необходимости передавать ей логин и пароль.

### JWT
Это стандарт создания токенов, на формате JSON. Используется для аутентификации в клиент-серверных приложениях. Токены создаются сервером, подписываются секретным ключом и передаются клиенту, кот. в дальнейшем используетс данный токен для подтверждения своей личности.