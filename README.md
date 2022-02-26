# UML
Быстрая навигация
--------------------

[Диаграммы UML](https://github.com/elisntdead/UML/blob/main/README.md#диаграммы)

[База данных](https://github.com/elisntdead/UML/blob/main/README.md#база-данных)

[Формы](https://github.com/elisntdead/UML/blob/main/README.md#формы)

<hr>
В этом репозитории собраны UML-диаграммы проекта для реализации упрощенной работы с предоставленем клиентам различных услуг.
Задача проекта ─ упростить и ускорить работу с различными элементами, с которыми работает организация.
Все в этом репозитории связанно с аналитикой, схематикой. Разработка программы не ведётся (или будет позднее).
<hr>
Ключевыми функциями программы являются:
<li>
простая и удобная работа с заказами
<li>
отслеживание статуса заказов
<li>
удобное ведение работы с партнерами, списком их услуг
<li>
работа со списком сотрудников
<li>
для клиента, простой способ самостоятельно отслеживать свои заказы
<hr>
  
Диаграммы
--------------------
  
Диаграма прецедентов
--------------------
  
  ![Диаграмма прецедентов](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_UseCases.png)
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  
Диаграмма классов
--------------------
  
  ![Диаграмма классов](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_Classes.png)
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
Диаграмма состояний
  --------------------
  
  ![Диаграмма состояний](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_State.png)
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
Диаграмма последовательности
--------------------
  
  ![Диаграмма последовательности](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_Sequence.png)
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
Диаграммы деятельности
--------------------
  
![Диаграмма деятельности (смена товара)](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_ActivityChangeProduct.png)
  
На первой диаграмме отражен процесс смены товара, во время того как заказ уже стал активным.
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
![Диаграмма деятельности (доставка)](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_ActivityDelivery.png)
  
На второй диаграмме отражен процесс доставки товара.
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)

Диаграмма кооперации
--------------------
![Диаграмма кооперации](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_Cooperation.png)
  
[Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
Диаграмма интерфейсов
--------------------
![Диаграмма интерфейсов](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_Interface.png)
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
База Данных
--------------------
Схема базы данных
--------------------
![Схема базы данных](https://github.com/elisntdead/UML/blob/main/images/Cherkasov_BD_shema.png)
  
[Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
Запросы SQL к базе данных
--------------------
Представленные ниже запросы являются примерами запросов к [этой БД](https://github.com/elisntdead/UML/blob/main/DB/Cherkasov_BD_SQL.db)
```
SELECT DISTINCT Orders.id
FROM Clients INNER JOIN Orders ON Clients.id = Orders.id_client
WHERE Clients.phone Like '7(999)%'
```
Заказы, номера клиентов которых начинаются с "7(999)".
```
SELECT Orders.id AS OrderID, Employees.id AS ENPLOYEEID
FROM Employees INNER JOIN Orders ON Employees.id = Orders.id_employee
WHERE Employees.id <> 6;
```
Заказы, которые не выполнял определённый сотрудник. В данном случае под 6 id.
```
SELECT DISTINCT Orders.id
FROM Orders INNER JOIN (Offers INNER JOIN OffersInOrder ON Offers.id = OffersInOrder.id_offer) ON Orders.id = OffersInOrder.id_order
WHERE Offers.name="Шарики";
```
Заказы, в которых отсутствуют товары с определенным названием. В данном случае "Шарики".
```
SELECT DISTINCT Orders.id
FROM Orders INNER JOIN (Offers INNER JOIN OffersInOrder ON Offers.id = OffersInOrder.id_offer) ON Orders.id = OffersInOrder.id_order
WHERE Offers.id<>3;  
```
Все заказы, кроме одного с определенным id. В данном случае 3 id.
```
SELECT Orders.id,  SUM(OffersInOrder.amount * OffersInOrder.price) AS orderPrice
FROM Orders INNER JOIN OffersInOrder ON Orders.id = OffersInOrder.id_order INNER JOIN Offers ON Offers.id = OffersInOrder.id_offer
GROUP BY Orders.id
ORDER BY orderPrice DESC
LIMIT 3;
```
Три самых дорогих заказа.

[Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)  
  
Формы
--------------------
Формы можно просмотреть в этом [файле](https://github.com/elisntdead/UML/blob/main/Forms/Cherkasov_Forms.bmpr), с помощью программы Balsamiq Mockups
  
[Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
Изоражения форм

![Окно входа](https://github.com/elisntdead/UML/blob/main/images/Login.png)
  
Окно входа
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Меню (клиента)](https://github.com/elisntdead/UML/blob/main/images/Main_menu_client.png)
  
  Меню (клиента)
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Меню (работника)](https://github.com/elisntdead/UML/blob/main/images/Main_menu_employee.png)
  
  Меню (работника)
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Настройки аккаунта](https://github.com/elisntdead/UML/blob/main/images/Account_Settings.png)
  
  Настройки аккаунта
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Просмотр клиентов](https://github.com/elisntdead/UML/blob/main/images/Clients.png)
  
  Просмотр клиентов
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Просмотр сотрудников](https://github.com/elisntdead/UML/blob/main/images/Employees.png)
  
  Просмотр сотрудников
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Просмотр заказов](https://github.com/elisntdead/UML/blob/main/images/Orders.png)
  
  Просмотр заказов
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Просмотр услуг](https://github.com/elisntdead/UML/blob/main/images/Offers.png)
  
  Просмотр услуг
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Просмотр партнёров](https://github.com/elisntdead/UML/blob/main/images/Partners.png)
  
  Просмотр партнеров
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Добавить\редактировать](https://github.com/elisntdead/UML/blob/main/images/Add_Edit_Client.png)
  
  Добавить\редактировать клиента
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Добавить\редактировать работника](https://github.com/elisntdead/UML/blob/main/images/Add_Edit_Employee.png)
  
  Добавить\редактировать работника
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Добавить\редактировать услугу](https://github.com/elisntdead/UML/blob/main/images/Add_Edit_Offer.png)
  
  Добавить\редактировать услугу
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Добавить\редактировать заказ](https://github.com/elisntdead/UML/blob/main/images/Add_Edit_Order.png)
  
  Добавить\редактировать заказ
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Добавить\редактировать партнера](https://github.com/elisntdead/UML/blob/main/images/Add_Edit_Partner.png)
  
  Добавить\редактировать партнера
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![ Просмотр клиента](https://github.com/elisntdead/UML/blob/main/images/View_Clients.png)
  
  Просмотр клиента
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![ Просмотр заказа](https://github.com/elisntdead/UML/blob/main/images/View_Order.png)
  
   Просмотр заказа
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Просмотр работника](https://github.com/elisntdead/UML/blob/main/images/View_Employee.png)
  
   Просмотр работника
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Просмотр услуги](https://github.com/elisntdead/UML/blob/main/images/View_Offer.png)
  
   Просмотр услуги
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
  
  ![Просмотр партнера](https://github.com/elisntdead/UML/blob/main/images/View_Partners.png)
  
   Просмотр партнера
  
  [Наверх](https://github.com/elisntdead/UML/blob/main/README.md#UML)
