# og-sale-bot

## Как запустить
Для работы требуется установленный Node.js v18 или выше (https://nodejs.org/en)

Первым делом скачиваем архив (Зеленая кнопка `Code` -> `Download ZIP`) и распаковываем.

Затем нужно открыть терминал (CMD или PowerShell на Windows) и перейти в папку где находится файл package.json.
<details>
  <summary>Как это сделать?</summary>

  В проводнике копируем путь к папке и вставляем в терминале:
  ```bash
  cd путь_к_папке
  ```
</details>

#### Далее выполняем следующие команды:

Установка зависимостей
```bash
npm install
```

Запуск
```bash
npm start
```

## Формат кошельков в wallets.txt
> **_ВАЖНО:_** Каждый кошелек нужно указать только один раз!

```txt
# Формат:
# PRIVATE_KEY;MIN_TIER-MAX_TIER;AMOUNT
#
# Где:
# PRIVATE_KEY   - Приватный ключ
# MIN_TIER      - Минимальный тир (от 1 до 32)
# MAX_TIER      - Максимальный тир (от 1 до 32)
# AMOUNT        - Желаемое количество нод
#
# Примеры:

0x00001;1-3;2 - Купить 1, 2 или 3 тир в количестве 2 шт.
0x00002;2;5   - Купить только 2 тир в количестве 5 шт.
```

## Как изменить/добавить другие RPC или поменять газ
В файле main.js сверху есть переменные RPC_PROVIDERS, MAX_FEE_PER_GAS и MAX_PRIORITY_FEE_PER_GAS

Также можно редактировать параметр STOP_ON_FIRST_PURCHASE.\
По умолчанию бот попробует купить один самый лучший тир и остановится как только его сможет купить.\
Если указать `STOP_ON_FIRST_PURCHASE = false`, тогда бот будет пытаться купить все указанные тиры по очереди.
