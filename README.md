# notesRESTNapoleonIT: Реализация web сервиса для работы с заметками
Необходимо создать HTTP API для взаимодействия с сервисом заметок. 

Модель заметки описана ниже:

| Поле |	Тип |	Описание |
|:------:|:-----:|:----------:|
| id|	String |	Строка в формате UUID |
| title|	String |	Заголовок заметки |
| date_create |	Int |	Время создания заметки в формате UNIX Time Stamp |
| date_update |	Int |	Время последнего редактирования заметки в формате UNIX Time Stamp |

JSON-объект заметки будет выглядеть следующим образом:<br>
{<br>
 “id”: “10dcdccb-8876-4245-ac53-92900c6509bd”,<br>
 “title”: “Текст заголовка”,<br>
 “text”: “Текст заметки”,<br>
 “date_create”: 1513759529,<br>
 “date_update”: 1517259529<br>
}<br><br>
**Описание машрутов**<br><br>
В рамках тестового задания нужно реализовать следующие маршруты:

**1) GET /notes/**<br><br>
Используется для получения списка всех заметок

Входные данные:<br>
Отсутствуют

Выходные данные:<br>
200 Ok

Массив объектов заметок (описание объекта заметки см. выше)

**2) POST /notes/**<br><br>
Используется для создания заметки

Входные данные:<br>
body:<br>
{<br>
   "title": "Тестовая заметка",<br>
   "text": "Текст тестовой заметки"<br>
}<br><br>
Выходные данные:<br>
201 Created

**3) GET /notes/<note_id>/**<br><br>
Используется для получения информации о заметке по ее идентификатору

Входные данные:<br>
note_id - String в формате UUID - идентификатор заметки, отправляется в path

Выходные данные:<br>
200 Ok

Объект заметки (описание объекта заметки см. выше)

**4) PUT /notes/<note_id>/**<br><br>
Входные данные:<br>
note_id - String в формате UUID - идентификатор заметки, отправляется в path

body:<br>
{<br>
   "title": "Тестовая заметка",<br>
   "text": "Текст тестовой заметки"<br>
}<br>
Выходные данные:<br>
200 Ok

Обновленный объект заметки (описание объекта заметки см. выше)

Требования к реализации<br>
Сервер должен быть доступен локально по адресу localhost и на порту 8080 (http://localhost:8080)
