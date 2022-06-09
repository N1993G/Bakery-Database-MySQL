-- CREATE A DATABASE CALLED 'BAKERY'
CREATE DATABASE Bakery;
USE Bakery;
-- ADD TWO TABLES TO THE DATABASE, ONE SHOULD BE CALLED 'SWEET' AND THE OTHER ONE SHOULD BE CALLED 'SAVOURY'
-- THE SWEET TABLE SHOULD HAVE THREE COLUMNS: ID (WHICH IS A NUMBER), ITEM_NAME (NAME OF PASTRY) AND PRICE (CAN BE EXPRESSED IN POUND AND PENNIES)
CREATE TABLE Sweet (
  id INT NOT NULL, 
  item_name VARCHAR(50) NOT NULL, 
  price FLOAT(2)
);
-- INCLUDE THE SAME COLUMNS IN THE SAVOURY TABLE.  IN ADDITION, ADD A COLUMN NAMED MAIN_INGREDIENT (IT WILL BE A DESCRIPTIVE WORD)
CREATE TABLE Savoury (
  id INT NOT NULL, 
  item_name VARCHAR(50) NOT NULL, 
  price FLOAT(2), 
  main_ingredient VARCHAR(50)
);
-- ADD DATA TO EACH TABLE
INSERT INTO Sweet (id, item_name, price) 
VALUES 
  (1, 'Doughnut', 0.50), 
  (2, 'Croissant', 0.75), 
  (3, 'Pain Au Chocolat', 0.55), 
  (4, 'Cinnamon Twirl', 0.45), 
  (5, 'Cannoli', 0.88), 
  (6, 'Apple Tart', 1.12);
INSERT INTO Savoury (
  id, item_name, price, main_ingredient
) 
VALUES 
  (1, 'Meat Pie', 1.25, 'Pork'), 
  (2, 'Sausage Roll', 1.00, NULL), 
  (3, 'Pasty', 2.45, 'Beef');
--  FIND ALL SAVOURY ITEMS THAT HAVE EITHER PORK OR BEEF FILLING
SELECT 
  sa.item_name 
FROM 
  Savoury sa 
WHERE 
  sa.main_ingredient = 'Pork' 
  OR 'Beef';
-- FIND ALL SWEET ITEMS THAT COST 0.50 OR CHEAPER
SELECT 
  * 
FROM 
  sweet sw 
WHERE 
  sw.price < 50;
-- FIND ALL SWEET ITEMS AND THEIR PRICE, EXCEPT FOR CANNOLI
SELECT 
  sw.item_name, 
  sw.price 
FROM 
  Sweet sw 
WHERE 
  sw.item_name != 'Cannoli';
--  FIND ITEMS FROM SWEET TABLE THAT START WITH THE LETTER 'C'
SELECT 
  sw.item_name 
FROM 
  Sweet sw 
WHERE 
  sw.item_name LIKE 'c%';
-- FIND ALL SAVOURY ITEMS THAT COST MORE THAN £1 BUT LESS THAN £3
SELECT 
  * 
FROM 
  Savoury s 
WHERE 
  s.price > 1 
  AND s.price < 3;
-- VIEW ALL PRICES FOR ITEMS FROM SAVOURY IN ASCENDING ORDER
SELECT 
  * 
FROM 
  Savoury 
ORDER BY 
  price ASC;
