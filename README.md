## Версии
- Minecraft: 1.20.1
- Fabric Loader: >=0.15.6
- Fabric API: 0.83.0+1.20.1
- Placeholder API: 2.1.3+1.20.1
- Java 17

## Конфиги и данные
- Конфиг: `${minecraftConfigDir}/1hp9lives/config.yml`
- Языковые файлы: `${minecraftConfigDir}/1hp9lives/lang/messages_ru.yml` и `messages_en.yml`
- База данных SQLite: `${minecraftConfigDir}/1hp9lives/1hp.db`

## Команды
- `/buylife [player] [count]` — покупка жизней с подтверждением (повышение цены после каждой покупки).
- `/buylife cancel` — отменить ожидающее подтверждение.
- `/pay_points <player> <points>` — перевести поинты.
- `/get_points <player> <points>` — (OP) установить поинты игроку.
- `/get_lifes <player> <life_count>` — (OP) установить жизни игроку.
- `/onexpmod reload` — (OP) перезагрузить конфиг и сообщения.

## Placeholder'ы (Placeholder API)
- `%onexpmod:points%` — количество поинтов.
- `%onexpmod:lives%` — количество жизней.

## Поведение
- За каждую **ачивку** игрок получает **10 поинтов**.
- **Тотем** списывает **50 поинтов** (настраивается).
- Цена жизни начинается со **100** и увеличивается на **50** после каждой покупки (индивидуально на игрока).
- Баланс может уходить в минус. Если поинты `<= -150`, игрок переводится в `spectator`, всем выводятся сообщения.
- При смерти:
  - всем в чат: `LifeLost`
  - лично игроку: `playerDeathMessage`
  - если это последняя жизнь: всем в чат `allLifesLost` и `lastDeathMessage`, плюс **сообщение на экране** (action bar).
