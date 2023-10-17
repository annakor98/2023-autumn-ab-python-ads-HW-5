# 2023-autumn-ab-python-ads-HW-5

## Общее описание

С помощью фреймворка FastAPI реализовать API на основе вашего проекта "Атака фродеров" (этап 2) по алгоритмам.

## API endpoints

| endpoint | Тип запроса | Тело запроса| Действие  | Примечание |
|----------|-------------|-------------|-----------|------------|
| ``/``    | GET         |             | Возвращает сообщение ``Hello! This is the fraud detector.``||
| ``/cost/{error_type}`` | GET         || Возващает стоимость ошибки I или II рода в рублях (``error_type`` должен принимает значения ``false-positive`` или ``false-negative``) | См. раздел Константы в Этапе 2 |
| ``/loss/{baseline}``| GET         || Оценивает потери маркетплейса при внедрении каждого бейзлайна в рублях (``baseline`` должен принимать значения ``constant-fraud``, ``constant-clean``, ``first-hypothesis``)  | См. раздел Бейзлайн и оценка качества в Этапе 2 |
| ``/predict/{baseline}`` | POST | Текст, для которого необходимо сделать предсказание fraud/clean ``{"text": "карты но водителя заявку и не закончилась сообщений ждать прошу отправителя Городе пытается Телеграм ее Получение ответьте написать передадим дозвонились. заберёт не транспортный дает получила"}`` | Возвращает предсказание класса (fraud/clean) для заданного входного текста| См. раздел Бейзлайн и оценка качества в Этапе 2 |

## Требования к содержанию репозитория с решением
* ``README.md`` с кратким описанием проекта
* ``main.py`` с реализованными endpoints
* ``model_predict.py`` с функциями для предсказания с помощью каждого из бейзлайнов ``constant-fraud``, ``constant-clean``, ``first-hypothesis``
* ``model_estimate.py`` с функциями, оценивающими потери в рублях для каждого из бейзлайнов ``constant-fraud``, ``constant-clean``, ``first-hypothesis``
* ``poetry.lock`` и ``pyproject.toml`` - создадутся автоматически при создании нового проекта в PyCharm с использованием poetry и установке зависимостей с помощью ``poetry add``
* ``schemas.py`` со всеми необходимыми схемами
* Файлы ``data_fraud.json`` и ``data_clean.json``

## Критерии оценки
* Реализованы все enpoints - 5 баллов
* В endpoint'ах ``/cost/{error_type}``, ``/loss/{baseline}``, ``/predict/{baseline}`` реализована правильная типизация параметров (только 2 возможных значения для ``error_type`` и 3 для ``baseline``). Request/response bodies реализованы с использованием ``pydantic.BaseModel`` - 2 балла
* В репозитории есть все необходимые файлы - 1 балл
