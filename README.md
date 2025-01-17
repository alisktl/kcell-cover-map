# kcell-cover-map

## Цели
- Автоматизировать процесс получения и обработки данных покрытия (geojson) из внешнего API (xPlan).
- Сжимать geojson данные через mapshaper внутри Docker-контейнера.
- Разделять данные по городам для дальнейшего использования.
- Сохранять обработанные данные в базе данных.
- Предоставлять обработанные данные через REST API фронтенд-приложению.

## Описание функциональности
### 1. Получение данных от xPlan
- Получать geojson файлы через предоставленный REST API endpoint.
- Выполнять запросы с учётом авторизации и возможных параметров фильтрации (например, выбор покрытия 4G/5G).

### 2. Сжатие geojson
- Сжимать файлы geojson с использованием инструмента mapshaper.
- Mapshaper должен быть установлен в Docker-контейнере, откуда будет вызван процесс сжатия через команду в терминале.

### 3. Разделение данных по городам
- Обрабатывать geojson, разделяя данные покрытия по городам (например, на основе атрибутов внутри geojson).
- Создавать отдельные файлы/структуры данных для каждого города.

### 4. Сохранение данных в базу данных
- Сохранять разделённые данные в реляционной (PostgreSQL).
- Учитывать возможность быстрого доступа к данным для каждого города.

### 5.Предоставление данных через REST API
- Разработать endpoint для получения geojson данных по заданному городу.
- API должен возвращать данные в формате geojson.

Для задач 1-4 использовать Temporal
