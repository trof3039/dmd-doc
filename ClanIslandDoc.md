# Clan Island API Documentation

## 1. Применение баффа зеркальной атаки

### Endpoint:

```
POST /clans/islands/buff/mirror-attack
```

### Request Body:

```json
{
  "mirrorAttackClanId": number
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

### Response:

```json
{
  "defenceTimestamp": number
}
```

### Описание:

Применяет бафф защиты для клана. `defenceTimestamp` указывает момент активации.

---

## 3. Сбор клановых гемов

### Endpoint:

```
POST /clans/islands/collect-gems
```

### Response:

```json
true | false
```

### Описание:

Позволяет собрать доступные гема для клана. Возвращает `true`, если успешно.

---

## 4. Генерация кланового острова

### Endpoint:

```
POST /clans/islands/generate
POST /clans/islands/generate/dev
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
  "id": number,
  "clanId": number,
  "multiplier": number,
  "gemsGeneratedCount": number,
  "gemsGeneratedTimestamp": number,
  "gemsStolenCount": number,
  "swapTimestamp": number,
  "totalGemsCollected": number
}
```

### Описание:

Создаёт новый остров для клана в продакшн-версии.
Для DEV окружения можно создавать неограниченное кол-во островов для клана.

---

## 5. Удаление кланового острова (DEV)

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
true | false
```

### Описание:

Удаляет тестовый остров клана.

---

## 6. Получение случайного острова для атаки

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
  "totalGemsCollected": number
}
```

### Описание:

Возвращает случайный остров, доступный для атаки.

---

## 7. Смена случайного острова для атаки

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
  "totalGemsCollected": number
}
```

### Описание:

Позволяет сменить остров, который будет атакован.

---

## 8. Атака на остров

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
`boosters` - список использованных бустеров.

---

## 9. Получение списка всех островов

### Endpoint:

```
POST /clans/islands
```

### Request Body:

```json
{
  "filters": { "key": any },
  "offset": number,
  "limit": number,
  "order": string
}
```

### Response:

```json
[
  {
    "id": number,
    "clanId": number,
    "multiplier": number,
    "gemsGeneratedCount": number,
    "gemsGeneratedTimestamp": number,
    "gemsStolenCount": number,
    "swapTimestamp": number,
    "totalGemsCollected": number
  }
]
```

### Описание:

Позволяет получить список всех островов с возможностью фильтрации и пагинации.