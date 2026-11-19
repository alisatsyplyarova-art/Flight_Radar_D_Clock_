Страница обновления прибора по USB (для GitHub Pages).

Положить в папку docs/flash/ репозитория:
  index.html
  manifest.json
  firmware.bin   <- образ приложения из Arduino IDE: Скетч -> Экспорт откомпилированного двоичного файла

Файл firmware.bin должен собираться с той же таблицей разделов (Huge APP) и версией, что указана в manifest.json.
Адрес записи в manifest.json: 65536 (0x10000). Настройки (NVS, 0x9000) не затрагиваются.

GitHub Pages: Settings -> Pages -> Deploy from a branch -> main, folder /docs.
Страница будет доступна по адресу https://<пользователь>.github.io/<репозиторий>/flash/
