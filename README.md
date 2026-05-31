1. Транспортные Средства
Описание
База данных моделирует каталог транспортных средств: автомобили, мотоциклы и велосипеды.
Используется для фильтрации, объединения и анализа характеристик различных типов транспорта.

Структура БД
Vehicle

model (PK)

maker

price

Car

model (PK, FK → Vehicle)

horsepower

engine_capacity

Motorcycle

model (PK, FK → Vehicle)

horsepower

engine_capacity

Bicycle

model (PK, FK → Vehicle)

gear_count

Реализованные задачи
Фильтрация и объединение данных

Сортировка и сравнение характеристик

2. Автомобильные Гонки
Описание
База данных моделирует участие автомобилей в гонках.
Используется для анализа результатов, определения лучших автомобилей и классов.

Структура БД
Classes

class (PK)

type

country

numDoors

engineSize

weight

Cars

name (PK)

class (FK → Classes)

year

Races

name (PK)

date

Results

car (FK → Cars)

race (FK → Races)

position

Реализованные задачи
Лучшие автомобили в каждом классе

Лучший автомобиль среди всех

Лучшие классы автомобилей

Автомобили лучше среднего по классу

Классы с наибольшим числом слабых автомобилей

3. Бронирование Отелей
Описание
База данных моделирует систему бронирования отелей: клиенты, номера, отели и бронирования.
Используется для анализа поведения клиентов, их предпочтений и финансовой активности.

Структура БД
Hotel

ID_hotel (PK)

name

location

Room

ID_room (PK)

ID_hotel (FK → Hotel)

room_type

price

capacity

Customer

ID_customer (PK)

name

email

phone

Booking

ID_booking (PK)

ID_room (FK → Room)

ID_customer (FK → Customer)

check_in_date

check_out_date

Реализованные задачи
Клиенты с более чем двумя бронированиями в разных отелях

Клиенты с расходами более 500 долларов

Предпочтения клиентов по типу отелей

4. Структура Организации
Описание
База данных моделирует структуру компании: отделы, роли, сотрудники, проекты и задачи.
Особенность — иерархия сотрудников через ManagerID, позволяющая строить рекурсивные отчёты.

Структура БД
Departments

DepartmentID (PK)

DepartmentName

Roles

RoleID (PK)

RoleName

Employees

EmployeeID (PK)

Name

Position

ManagerID (FK → Employees)

DepartmentID (FK → Departments)

RoleID (FK → Roles)

Projects

ProjectID (PK)

ProjectName

StartDate

EndDate

DepartmentID (FK → Departments)

Tasks

TaskID (PK)

TaskName

AssignedTo (FK → Employees)

ProjectID (FK → Projects)

Реализованные задачи
Иерархия подчинённых Ивана Иванова

Подчинённые + задачи + прямые подчинённые

Менеджеры с подчинёнными (включая вложенных)

Цель проекта
Проект демонстрирует:

проектирование реляционных структур,

работу с внешними ключами и каскадными ограничениями,

построение рекурсивных SQL‑запросов,

анализ и агрегацию данных,

создание аналитических отчётов на основе нескольких связанных таблиц.
