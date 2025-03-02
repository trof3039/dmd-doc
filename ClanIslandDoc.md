# Clan Island API Documentation

## 1. Применение баффа зеркальной атаки

### Endpoint:

```
POST /clans/islands/buff/mirror-attack
```

### Request Body:

```json
{
  "mirrorAttackClanId": number,
  "clanId": number
}
```

### Response:

```json
{
  "mirrorAttackTimestamp": number,
  "mirrorAttackClanId": number
}
```

### Описание:

Позволяет клану активировать бафф зеркальной атаки против указанного `mirrorAttackClanId`.
`mirrorAttackTimestamp` указывает время активации баффа.

---

## 2. Применение баффа защиты

### Endpoint:

```
POST /clans/islands/buff/defence-multiplier
```

### Request Body:

```json
{
  "clanId": number
}
```

### Response:

```json
{
  "defenceTimestamp": number
}
```

### Описание:

Применяет бафф защиты для клана. `defenceTimestamp` указывает момент активации.

---

## 3. Применение баффа множителя гемов

### Endpoint:

```
POST /clans/islands/buff/gems-multiplier
```

### Request Body:

```json
{
  "clanId": number
}
```

### Response:

### Response:

```json
{
  "gemsMultiplierTimestamp": number
}
```

### Описание:

Активирует множитель гемов для клана. `gemsMultiplierTimestamp` указывает момент активации.

---

## 4. Сбор клановых гемов

### Endpoint:

```
POST /clans/islands/collect-gems
```

### Request Body:

```json
{
  "islandId": number
}
```

### Response:

```json
true
```

### Описание:

Позволяет собрать доступные гема для клана. Возвращает `true`, если успешно.

---

## 5. Генерация кланового острова

### Endpoint:

```
POST /clans/islands/generate
```

### Response:

```json
{
  "id": number,
  "clanId": number,
  "multiplier": number,
  "gemsGeneratedCount": number,
  "gemsGeneratedTimestamp": number,
  "gemsStolenCount": number,
  "swapTimestamp": number,
  "totalGemsCollected": number,
  "attacksCount": number
}
```

### Описание:

Создаёт новый остров для клана.

---

## 6. Удаление кланового острова (DEV)

### Endpoint:

```
POST /clans/islands/delete/dev
```

### Request Body:

```json
{
  "islandId": number
}
```

### Response:

```json
true
```

### Описание:

Удаляет тестовый остров клана.

---

## 7. Получение случайного острова для атаки

### Endpoint:

```
POST /clans/islands/attack/get-random-island
```

### Response:

```json

{
  "id": number,
  "clanId": number,
  "multiplier": number,
  "gemsGeneratedCount": number,
  "gemsGeneratedTimestamp": number,
  "gemsStolenCount": number,
  "swapTimestamp": number,
  "totalGemsCollected": number,
  "attacksCount": number,
  "clan": {
    "id": number,
    "name": string,
    "icon": string,
    "power": number
  },
  "swapProbabilityTier": number,
  "maxPossibleSteal": number,
  "minPossibleSteal": number
}

```

### Описание:

Возвращает случайный остров, доступный для атаки.

---

## 8. Смена случайного острова для атаки

### Endpoint:

```
POST /clans/islands/attack/change-random-island
```

### Response:

```json
{
  "id": number,
  "clanId": number,
  "multiplier": number,
  "gemsGeneratedCount": number,
  "gemsGeneratedTimestamp": number,
  "gemsStolenCount": number,
  "swapTimestamp": number,
  "totalGemsCollected": number,
  "attacksCount": number,
  "clan": {
    "id": number,
    "name": string,
    "icon": string,
    "power": number
  },
  "swapProbabilityTier": number,
  "maxPossibleSteal": number,
  "minPossibleSteal": number
}
```

### Описание:

Позволяет сменить остров, который будет атакован.

---

## 9. Атака на остров

### Endpoint:

```
POST /clans/islands/attack
```

### Request Body:

```json
{
  "targetIslandId": number,
  "boosters": string[]
}
```

### Response:

```json
{ 
  "gemsStolen": number, 
  "swapped": boolean 
}
```

### Описание:

Позволяет атаковать остров другого клана.

---

## 10. Получение информации о текущем острове клана

### Endpoint:

```
POST /clans/islands/my
```

### Response:

```json
{
  "id": number,
  "clanId": number,
  "multiplier": number,
  "gemsGeneratedCount": number,
  "gemsGeneratedTimestamp": number,
  "gemsStolenCount": number,
  "swapTimestamp": number,
  "totalGemsCollected": number,
  "attacksCount": number,
  "config": {
    "defenceMultiplierPrice": number,
    "defenceMultiplierDuration": number,
    "mirrorAttackPrice": number,
    "mirrorAttackDuration": number,
    "gemsMultiplierPrice": number,
    "gemsMultiplierDuration": number,
    "gemCollectionCD": number,
    "swapImmumityDuration": number,
    "changeRandomIslandPrice": number,
    "boosters": string[]
  }
}
```

### Описание:

Возвращает информацию о текущем острове клана.

## 11. Добавление персонального бустера (DEV)

### Endpoint:

```
POST /clans/islands/add-boosters/dev
```

### Request Body:

```json
{
  "boosters": string[]
}
```

### Response:

```json
true
```