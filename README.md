# Bakery Database SQL
 My first database created in MySQL Workbench with Code First Girls

CREATE DATABASE Bakery;
USE Bakery;
CREATE TABLE Sweet (
id INT NOT NULL,
item_name VARCHAR(50) NOT NULL,
price FLOAT(2)
);
CREATE TABLE Savoury (
id INT NOT NULL,
item_name VARCHAR(50) NOT NULL,
price FLOAT(2),
main_ingredient VARCHAR(50)
);
INSERT INTO Sweet
(id, item_name, price)
VALUES
(1, 'Doughnut', 0.50),
(2, 'Croissant', 0.75),
(3, 'Pain Au Chocolat', 0.55),
(4, 'Cinnamon Twirl', 0.45),
(5, 'Cannoli', 0.88),
(6, 'Apple Tart', 1.12);
INSERT INTO Savoury
(id, item_name, price, main_ingredient)
VALUES
(1, 'Meat Pie', 1.25, 'Pork'),
(2, 'Sausage Roll', 1.00, NULL),
(3, 'Pasty', 2.45, 'Beef');