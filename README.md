# 2023-autumn-ab-python-ads-HW-5

## API endpoints

| endpoint         | Тип запроса | Тело запроса                                                                                                 | Действие                                                                            |
|------------------|-------------|--------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| /                | GET         |                                                                                                              | Возвращает сообщение ``Hello! This is the fraud classifier.``                         |
| /cost/{error_type} | GET         |                                                                                                              | Возващает стоимость ошибки I или II рода в рублях (error_type должен принимает значения false-positive или false-negative)                                       |
| /loss/{baseline}           | GET         |                                                                                                              | Оценивает потери маркетплейса при внедрении каждого бейзлайна в рублях (baseline должен принимать значения constant-fraud, constant-clean, first-hypothesis)  |
| /predict/{baseline}         | POST        | Текст, для которого необходимо сделать предсказание fraud/clean ``{"text": "карты но водителя заявку и не закончилась сообщений ждать прошу отправителя Городе пытается Телеграм ее Получение ответьте написать передадим дозвонились. заберёт не транспортный дает получила~"}`` | Возвращает предсказание класса (fraud/clean) для заданного входного текста                          |
