# Module-2
Домашнее задание по модулю 2 курса Data Learn

Загрузка данных в БД
---

Загрузила данные из [модуля 1](https://github.com/EkaterinaSovetkina/DE-101-Module1) в базу данных MySQL. Использовала SQL-клиент DBeaver.

``` js
CREATE TABLE orders(
   Row_ID        INTEGER  NOT NULL PRIMARY KEY 
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
```



SQL-запросы
---

Ответила на вопросы из [модуля 1](https://github.com/EkaterinaSovetkina/DE-101-Module1)
