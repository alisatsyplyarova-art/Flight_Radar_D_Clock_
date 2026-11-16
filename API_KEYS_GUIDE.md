# Flight Radar-D & Clock — регистрация и API-ключи / API keys and registration

**Версия прошивки / Firmware version: 1.1.92**

Файл содержит две части: русскую и английскую. Они совпадают с разделом 9 подробной инструкции. Не публикуйте `Client Secret`, токены и ключи API.

The file has two parts: Russian and English. They match section 9 of the detailed guide. Do not publish `Client Secret`, tokens or API keys.

---

## Русская версия

### 9. Регистрация и API-ключи

Ниже — пошаговая регистрация для сервисов, которым нужны учётные данные. Адреса и названия разделов на сайтах со временем меняются, поэтому при расхождении ориентируйтесь на официальную справку сервиса. Не отправляйте ключи на сторонние сайты и не публикуйте их.

#### 9.1. OpenSky Network (бесплатно, OAuth2)

1.  Откройте официальный сайт **opensky-network.org** и зарегистрируйтесь или войдите в аккаунт.
2.  На странице аккаунта найдите раздел **API Clients** и создайте новый API-клиент.
3.  Скачайте выданный файл **credentials.json**. Он содержит поля `clientId` и `clientSecret`.
4.  На приборе откройте **«Источники данных» → OpenSky → «Загрузить credentials.json»**, выберите файл и подтвердите.
5.  Если не хотите загружать файл, введите Client ID вручную, а Client Secret — в защищённое поле на странице источников.
6.  Проверьте, что флажок **«Использовать OpenSky»** установлен, и нажмите «Сохранить».

OpenSky использует OAuth2 Client Credentials. Логин и пароль от сайта для прибора не подходят — нужны именно Client ID и Client Secret API-клиента. Официальная документация по авторизации: openskynetwork.github.io/opensky-api/rest.html

#### 9.2. Flightradar24 API (платный)

Для этого источника нужна **отдельная подписка именно на API** с API-кредитами. Обычная подписка на сайт Flightradar24 доступа к API не даёт.

1.  Откройте портал Flightradar24 API (fr24api.flightradar24.com) и создайте аккаунт или войдите.
2.  Перейдите в раздел **Subscription & credits** и выберите и активируйте API-план.
3.  Откройте **Key management** и нажмите **Create token**. Сохраните токен сразу в надёжном месте — значение может больше не показываться.
4.  На приборе откройте «Источники данных» → Flightradar24, вставьте токен в поле **API token** и нажмите «Сохранить».

Документация: fr24api.flightradar24.com/docs/getting-started и fr24api.flightradar24.com/docs/authentication

#### 9.3. OpenWeatherMap (погода, бесплатный ключ)

1.  Откройте сайт **openweathermap.org** и зарегистрируйтесь.
2.  Подтвердите адрес электронной почты: письмо приходит на почту, которую вы указали.
3.  В личном кабинете откройте раздел **API keys** и скопируйте ключ. Ключ может появиться не сразу, иногда через некоторое время после регистрации.
4.  На приборе откройте «Источники» → «Настройка источников погоды», выберите OpenWeatherMap и вставьте ключ в поле. Нажмите «Сохранить».

По описанию в этой инструкции бесплатный тариф не требует карты, но условия могут меняться — проверьте их на сайте перед регистрацией.

#### 9.4. WeatherStack (погода, бесплатный ключ)

1.  Откройте сайт **weatherstack.com** и зарегистрируйтесь на бесплатный тариф.
2.  Скопируйте **Access Key** из личного кабинета.
3.  На приборе откройте «Настройка источников погоды», выберите WeatherStack и вставьте ключ. Нажмите «Сохранить».

Бесплатный тариф ограничен количеством запросов в месяц, поэтому прибор обновляет погоду раз в 8 часов.

#### 9.5. Источники без ключей

Для этих источников регистрация не нужна: **Open-Meteo**, **NOAA METAR** (aviationweather.gov), **adsb.fi**, **airplanes.live**, **adsb.lol**, **adsb.one**. Соблюдайте лимиты и условия использования каждого сервиса.

#### 9.6. Где хранятся ключи

- Ключи и токены хранятся в памяти прибора.
- В файл резервной копии настроек ключи **не попадают**. После восстановления из файла проверьте их на странице погоды и на странице источников.
- Файл **credentials.json** от OpenSky — секретный. Не публикуйте его и не отправляйте посторонним.

### Безопасность и резервные копии

- Общая JSON-резервная копия Flight Radar-D & Clock не содержит пароль Wi-Fi, OpenSky Client ID/Secret или токен Flightradar24.
- OpenSky `credentials.json` — отдельный файл с секретом; не добавляйте его в репозиторий и не отправляйте посторонним.
- При импорте OpenSky JSON устройство сохраняет Client ID/Secret в энергонезависимую память NVS. После загрузки файл не показывается и не выводится в Serial Monitor.
- Файлы credentials не включаются в общую резервную копию. При переносе устройства на другую плату импортируйте credentials.json отдельно.

---

## English version

### 9. Registration and API keys

Below are step-by-step instructions for services that need credentials. Site addresses and section names change over time, so if something differs, follow the service's official help. Do not send keys to third-party sites and do not publish them.

#### 9.1. OpenSky Network (free, OAuth2)

1.  Open the official site **opensky-network.org** and sign up or log in.
2.  On your account page find the **API Clients** section and create a new API client.
3.  Download the issued file **credentials.json**. It contains the fields `clientId` and `clientSecret`.
4.  On the device open **Data sources → OpenSky → "Upload credentials.json"**, choose the file and confirm.
5.  If you do not want to upload the file, type the Client ID manually and enter the Client Secret in the protected field on the sources page.
6.  Make sure the **"Use OpenSky"** checkbox is ticked and press "Save".

OpenSky uses OAuth2 Client Credentials. Your website login and password do not work for the device — you need the Client ID and Client Secret of the API client. Official authentication documentation: openskynetwork.github.io/opensky-api/rest.html

#### 9.2. Flightradar24 API (paid)

This source needs a **separate API subscription** with API credits. A regular Flightradar24 website subscription does not give API access.

1.  Open the Flightradar24 API portal (fr24api.flightradar24.com), sign up or log in.
2.  Go to **Subscription & credits** and choose and activate an API plan.
3.  Open **Key management** and press **Create token**. Save the token somewhere safe immediately — the value may not be shown again.
4.  On the device open Data sources → Flightradar24, paste the token into the **API token** field and press "Save".

Documentation: fr24api.flightradar24.com/docs/getting-started and fr24api.flightradar24.com/docs/authentication

#### 9.3. OpenWeatherMap (weather, free key)

1.  Open **openweathermap.org** and sign up.
2.  Confirm your email address: the message is sent to the address you entered.
3.  In your account open the **API keys** section and copy the key. The key may appear with a delay after registration.
4.  On the device open "Sources" → "Weather provider settings", choose OpenWeatherMap and paste the key. Press "Save".

As described in this manual, the free plan does not require a card, but terms can change — check them on the site before signing up.

#### 9.4. WeatherStack (weather, free key)

1.  Open **weatherstack.com** and sign up for the free plan.
2.  Copy the **Access Key** from your account dashboard.
3.  On the device open "Weather provider settings", choose WeatherStack and paste the key. Press "Save".

The free plan is limited in requests per month, so the device updates the weather every 8 hours.

#### 9.5. Sources without keys

No registration is needed for: **Open-Meteo**, **NOAA METAR** (aviationweather.gov), **adsb.fi**, **airplanes.live**, **adsb.lol**, **adsb.one**. Follow the limits and terms of each service.

#### 9.6. Where keys are stored

- Keys and tokens are stored in the device memory.
- Keys are **not** included in the settings backup file. After restoring from a file, check them on the weather page and the sources page.
- The OpenSky **credentials.json** file is secret. Do not publish it or send it to anyone.

### Security and backups

- The general JSON backup of Flight Radar-D & Clock does not contain the Wi-Fi password, OpenSky Client ID/Secret or the Flightradar24 token.
- The OpenSky `credentials.json` is a separate file containing a secret; do not add it to a repository or share it with anyone.
- When you import an OpenSky JSON file, the device stores the Client ID/Secret in non-volatile memory (NVS). After loading, the file is not shown and is not printed to the Serial Monitor.
- Credentials files are not included in the general backup. When moving the device to another board, import credentials.json separately.
