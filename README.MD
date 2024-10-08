# :musical_note: Spotigram

<img src="spotigram.png" alt="logo" width="300" height="300">


![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/arseniizyk/Spotigram)
![GitHub top language](https://img.shields.io/github/languages/top/arseniizyk/Spotigram)
![GitHub last commit](https://img.shields.io/github/last-commit/arseniizyk/Spotigram)

**Spotigram is app made to sync tracks from Spotify to Telegram Bio**
___

## Язык (Language)
  - **[RU](#ru)**
  - **[EN](#en)**


## <span id="ru">Русский</span>

### Установка

**1. Зарегистрировать [Telegram приложение](https://my.telegram.org/auth?to=apps), сохранить `api_id` и `api_hash`(но не публиковать, т.к потом нельзя будет изменить), зарегистрировать [Spotify приложение](https://developer.spotify.com/dashboard), сохранить `client_id` и `client_secret`, но так же не публиковать в общий доступ**

**2. Скачать и скомпилировать TDlib библиотеку при помощи [TDlib build instructions](https://tdlib.github.io/td/build.html). После компиляции перенести все `.dll` файлы из `tdlib/bin` в `cmd/app/`, они так же необходимы если запускать через `.exe`**

**3. Для запуска необходимо указать папку с tdlib в переменную среды**

  + Powershell:
    ```Powershell
    $env:CGO_ENABLED=1; 
    $env:CGO_CFLAGS="-IC:/td/tdlib/include"; 
    $env:CGO_LDFLAGS="-LC:/td/tdlib/bin -ltdjson"
    ```

**4. Создать `.env` файл в директории `cmd/app`, в который добавить токены полученные на 1 шаге**

+ .env
  ```env
  SPOTIFY_CLIENT_ID=YOUR_SPOTIFY_CLIENT_ID
  SPOTIFY_CLIENT_SECRET=YOUR_SPOTIFY_CLIENT_SECRET
  TELEGRAM_API_ID=YOUR_TELEGRAM_API_ID
  TELEGRAM_API_HASH=YOUR_TG_API_HASH
  ```

### Использование
**При первом запуске приложение создает директории `.tdlib` и `/database`, где будут храниться логины телеграмма и спотифая, далее вводить данные не придется, обновляться токены будут сами при запуске**

**Работа со Spotify происходит через [Spotify API](https://developer.spotify.com/documentation/web-api) <br>C Telegram через [TDlib](https://core.telegram.org/tdlib), при помощи [go-tdlib](https://github.com/zelenin/go-tdlib)**

___

## <span id="en">English</span>
### **Installation**

**1. Register [Telegram app](https://my.telegram.org/auth?to=apps) save `api_id` and `api_hash`(dont publish cuz you cant change it) and register [Spotify app](https://developer.spotify.com/dashboard), save `client_id` and `client_secret` but also dont publish it**

**2. Download and compile TDlib using [TDlib build instructions](https://tdlib.github.io/td/build.html). After compilation move all `.dll` files from `tdlib/bin` to `cmd/app/`, they are also needed to run `.exe`**

**3. To run app, you should define folder with TDlib in the environment variables**


  + Powershell:
    ```Powershell
    $env:CGO_ENABLED=1; 
    $env:CGO_CFLAGS="-IC:/td/tdlib/include"; 
    $env:CGO_LDFLAGS="-LC:/td/tdlib/bin -ltdjson"
    ```

**4. Create .env file in `cmd/app` with tokens from 1 step**

+ .env
  ```env
  SPOTIFY_CLIENT_ID=YOUR_SPOTIFY_CLIENT_ID
  SPOTIFY_CLIENT_SECRET=YOUR_SPOTIFY_CLIENT_SECRET
  TELEGRAM_API_ID=YOUR_TELEGRAM_API_ID
  TELEGRAM_API_HASH=YOUR_TG_API_HASH
  ```

### **Usage**
___
**Upon the first launch, the application creates the directories `.tdlib` and `/database`, where the Telegram and Spotify logins will be stored. You won’t need to enter the data again.**

**Interaction with Spotify is done through the [Spotify API](https://developer.spotify.com/documentation/web-api) <br>And with Telegram through [TDlib](https://core.telegram.org/tdlib) using [go-tdlib](https://github.com/zelenin/go-tdlib)**

