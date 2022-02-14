# choco-frontend-auth

## Запуск проект локально (npm)

```
npm run install
npm run serve
```

## Запуск проект локально (npm)

```
yarn install
yarn serve
```

## TODO

1. Сохранить полученный токен в localStorage или Cookies
2. При обновлении страницы если есть токен, то показывать профиль пользователя
3. Проверить валидность токена (дата истечения)
4. Дополнительно: использовать токен в axios.interceptors, а не назначать его вручную: api.defaults.headers.common["Authorization"]
