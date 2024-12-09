# Задание 1

## 1 выбор подхода

 Выбрал Webpack Module Federation, тк приложение использует один фреймворк (React). Можно сказать, что экспертизы больше в webpack (как мимнимум в рамках курса описывается пример создания микросервисов через Module Federation). Так же несколько страниц документации, и можно уже настроить федерации. Учитывая огромное комьюнити, конфиг самого вебпака можно подглядеть в интернете + есть репозиторий с кучей примеров реализации.  

## 2 реализация структуры

host 

/auth-microfrontend
  /src
    /components
      App.js               // App файл, должен уменшиться за счет микрофронтов
      Main.js              // Главный компонет с отоброжением микросервисов профиля и аватара + кнопка добавления нового места и мапинг карт 
    /styles
      ---
    /utils
      api.js                // api информации по пользователю и получения списка карт
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js

  <!-- Контекст я бы убрал и апилировал API в микросервисах -->

microfrontend

/auth-microfrontend
  /src
    /components
      Login.js               // Компонент входа пользователя
      Register.js            // Компонент регистрации пользователя
      InfoTooltip.js         // Статус регистрации
    /styles
      login.css              // Стили для компонента входа
      register.css           // Стили для компонента регистрации
    /utils
      auth.js                // Утилиты для аутентификации
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js
  
/profile-microfrontend
  /src
    /components
      ProfileInfo.js          // информация о пользователе из Main.js (profile__info)
      EditProfilePopup.js     // Модалка с данными пользователя
   /utils
      api.js                // api информации по пользователю getUserInfo, setUserInfo
    /styles
     ---
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js
  
/avatar-microfrontend
  /src
    /components
      Avatar.js               // аватар с обработчиком из Main.js (profile__image)
      EditAvatarPopup.js     // Модалка с изменением аватара
    /utils
       api.js                // api информации по пользователю, setUserAvatar 
    /images  
    /styles
     ---
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js
  
/cards-microfrontend
  /src
    /components
      Card.js     // Компонет карточки
      ImagePopup.js // Карточка в раскрытом виде
    /utils
      api.js                // api removeCard, changeLikeCardStatus
    /images  
    /styles
     ---
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js

  
/add-place-microfrontend
  /src
    /components
      AddPlacePopup.js     // Модалка добавления новой карточки
    /styles
     ---
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js

  
/header-microfrontend
  /src
    /components
      Header.js     // шапка страницы
  
   /utils
      api.js                // api addCard
    /styles
     ---
   /images  
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js

/footer-microfrontend
  /src
    /components
      Footer.js     // футер страницы
    /styles
     ---
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js

/popup-with-form-microfrontend
  /src
    /components
      PopupWithForm.js     // Общий компонет для создания форм (используют другие микросервисы)
    /styles
     ---
    index.js                 // Точка входа микрофронтенда
  package.json               // Зависимости и скрипты микрофронтенда
  README.md                  // Описание сервиса
  webpack.config.js







