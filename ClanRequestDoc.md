## 1. Включение/отключение приема заявок в клан

### Endpoint:

```
POST /clans/requests/accept
```

### Request Body:

```json
{
  "acceptRequests": boolean
}
```

### Response:

```json
true
```

---

## 2. Получение списка заявок в клан

### Endpoint:

```
POST /clans/requests/list
```

### Request Body:

_(пустое тело запроса)_

### Response:

```json
[
  {
    "id": number,
    "clanId": number,
    "playerId": number,
    "approved": boolean | null,
    "createdAt": number,
    "updatedAt": number
  }
]
```

---

## 3. Отправка запроса на вступление в клан

### Endpoint:

```
POST /clans/requests/join
```

### Request Body:

```json
{
  "clanId": number
}
```

### Response:

```json
true
```

---

## 4. Одобрение заявки на вступление в клан

### Endpoint:

```
POST /clans/requests/approve
```

### Request Body:

```json
{
  "playerId": number
}
```

### Response:

```json
true
```

---

## 5. Отклонение заявки на вступление в клан

### Endpoint:

```
POST /clans/requests/decline
```

### Request Body:

```json
{
  "playerId": number
}
```

### Response:

```json
true
```

---

## 6. Отклонение всех заявок в клан

### Endpoint:

```
POST /clans/requests/decline-all
```

### Request Body:

```json
{
  "playerId": number
}
```

### Response:

```json
true
```

