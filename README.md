# Сайт-заглушка для нод
 
Сайт-заглушка, разворачиваемый на ноде.
 
## Установка
 
### 1. Сгенерировать сертификат
 
Выпустить сертификат на домен через certbot на ноде:
 
```bash
certbot certonly --standalone -d site.example.com
```
 
### 2. Настроить окружение
 
```bash
cp .env.example .env
```
 
Открыть `.env` и заполнить `domain`.
 
### 3. Запустить
 
```bash
docker compose up -d
```

### 5. Проверить на хосте

```bash
curl -v \
  --resolve site.example.com:9443:127.0.0.1 \
  https://site.example.com:9443
```
 
### 6. Настроить Xray
 
В конфиге Xray указать target:
 
```
127.0.0.1:9443
```
 
