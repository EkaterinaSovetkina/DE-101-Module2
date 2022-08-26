# Module-2
Домашнее задание по модулю 2 курса Data Learn

Загрузка данных в БД
---

Загрузила данные из [модуля 1](https://github.com/EkaterinaSovetkina/DE-101-Module1) в базу данных MySQL. Использовала SQL-клиент DBeaver.

``` js
CREATE TABLE orders(
   Row_ID        INTEGER  NOT NULL PRIMARY KEY AUTO_INCREMENT
  ,Order_ID      VARCHAR(14) NOT NULL
  ,Order_Date    DATE  NOT NULL
  ,Ship_Date     DATE  NOT NULL
  ,Ship_Mode     VARCHAR(14) NOT NULL
  ,Customer_ID   VARCHAR(8) NOT NULL
  ,Customer_Name VARCHAR(22) NOT NULL
  ,Segment       VARCHAR(11) NOT NULL
  ,Country       VARCHAR(13) NOT NULL
  ,City          VARCHAR(17) NOT NULL
  ,State         VARCHAR(20) NOT NULL
  ,Postal_Code   INTEGER 
  ,Region        VARCHAR(7) NOT NULL
  ,Product_ID    VARCHAR(15) NOT NULL
  ,Category      VARCHAR(15) NOT NULL
  ,SubCategory   VARCHAR(11) NOT NULL
  ,Product_Name  VARCHAR(127) NOT NULL
  ,Sales         NUMERIC(9,4) NOT NULL
  ,Quantity      INTEGER  NOT NULL
  ,Discount      NUMERIC(4,2) NOT NULL
  ,Profit        NUMERIC(21,16) NOT NULL
);
INSERT INTO orders(Order_ID,Order_Date,Ship_Date,Ship_Mode,Customer_ID,Customer_Name,Segment,Country,City,State,Postal_Code,Region,Product_ID,Category,SubCategory,Product_Name,Sales,Quantity,Discount,Profit) VALUES ('CA-2018-152156','2018-11-08','2018-11-11','Second Class','CG-12520','Claire Gute','Consumer','United States','Henderson','Kentucky',42420,'South','FUR-BO-10001798','Furniture','Bookcases','Bush Somerset Collection Bookcase',261.96,2,0,41.9136);	
INSERT INTO orders(Order_ID,Order_Date,Ship_Date,Ship_Mode,Customer_ID,Customer_Name,Segment,Country,City,State,Postal_Code,Region,Product_ID,Category,SubCategory,Product_Name,Sales,Quantity,Discount,Profit) VALUES ('CA-2018-152156','2018-11-08','2018-11-11','Second Class','CG-12520','Claire Gute','Consumer','United States','Henderson','Kentucky',42420,'South','FUR-CH-10000454','Furniture','Chairs','Hon Deluxe Fabric Upholstered Stacking Chairs, Rounded Back',	731.94,3,0,219.582	);	
...
```

Результат

![Снимок экрана 2022-08-25 123156](https://user-images.githubusercontent.com/108063450/186616667-cfce9da1-3325-4625-a3ce-46b40d3b5d8f.png)


SQL-запросы
---

Ответила на вопросы из [модуля 1](https://github.com/EkaterinaSovetkina/DE-101-Module1).

**Прибыль по категориям за 2018 год.**

SQL-запрос
``` js
select Category as 'Категория', sum(Profit) as 'Прибыль'
from orders 
where Order_Date between '2018-01-01' and '2018-12-31'
group by Category;
```

Результат

![Снимок экрана 2022-08-25 160051](https://user-images.githubusercontent.com/108063450/186658922-bb65f935-d432-44bf-8c2a-3d7b3e619833.png)


**Распределение прибыли по штатам за 2018 год по убыванию.**

SQL-запрос
``` js
select State as 'Штат', sum(Profit) as Sum_of_profit 
from orders 
where Order_Date between '2018-01-01' and '2018-12-31'
group by State
order by Sum_of_profit desc ;
```

Результат

![Снимок экрана 2022-08-25 163449](https://user-images.githubusercontent.com/108063450/186666054-7b04e713-9d92-4804-84cf-4aa3b9eba3ff.png)

**Максимальная прибыль по подкатегориям по убыванию.**

SQL-запрос
``` js
select distinct SubCategory, max(Profit)
over (partition by SubCategory) as 'Max_Profit'
from orders o 
order by Max_Profit desc ;
```

Результат

![Снимок экрана 2022-08-26 122932](https://user-images.githubusercontent.com/108063450/186858986-6413a8bf-25a2-4c5f-b3a5-64ad7e6b8197.png)

