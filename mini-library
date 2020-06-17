DROP DATABASE IF EXISTS `mini-library`;
CREATE DATABASE `mini-library`;
USE `mini-library`;

CREATE TABLE `books` (
  `book_id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(1000) NOT NULL,
  `author` varchar(50) NOT NULL,
  `year` int NOT NULL,
  `price` decimal(4,2) NOT NULL,
  PRIMARY KEY (`book_id`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
INSERT INTO `books` VALUES (1,'How to Be an AntiracistHow to Be an Antiracist','Ibram X. Kendi',2020,20);
INSERT INTO `books` VALUES (2,'Saint X: A NovelSaint X: A NovelSaint X: A Novel','Alexis Schaitkin',2018,13);
INSERT INTO `books` VALUES (3,'The Day You BeginThe Day You BeginThe Day You Begin', 'Michelle Alexander',2016,25);
INSERT INTO `books` VALUES (4,'The New Jim Crow: Mass Incarceration in the Age of ColorblindnessThe New Jim Crow','Jacqueline Woodson',2020,10);
INSERT INTO `books` VALUES (5,'The World Needs More Purple PeopleThe World Needs More Purple People','Kristen Bell',2019,5);


CREATE TABLE `staff` (
  `staff_id` smallint(6) NOT NULL AUTO_INCREMENT,
  `name` varchar(50) NOT NULL,
  `salary` int(5),
  `age` int(2),
  `job` varchar(50) NOT NULL,
  PRIMARY KEY (`staff_id`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
INSERT INTO `staff` VALUES (1,'kamal',1900,22,'book organizer');
INSERT INTO `staff` VALUES (2,'samer',3000,30,'sales management');
INSERT INTO `staff` VALUES (3,'fahd',2000,19,'shipper');
INSERT INTO `staff` VALUES (4,'belal',2000,17,'shipper');
INSERT INTO `staff` VALUES (5,'zeinb',5900,44,'manager');


CREATE TABLE `customers` (
  `customer_id` int(11) NOT NULL AUTO_INCREMENT,
  `first_name` varchar(50) NOT NULL,
  `last_name` varchar(50) NOT NULL,
  `age` int(2) DEFAULT NULL,
  `phone` varchar(50) DEFAULT NULL,
  `address` varchar(50) NOT NULL,
  PRIMARY KEY (`customer_id`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
INSERT INTO `customers` VALUES (1,'eman','emad',19,null,'0 elglaa st');
INSERT INTO `customers` VALUES (2,'fady','mohamed',22,'01252985695','78 sakha st');
INSERT INTO `customers` VALUES (3,'salem','khaled',29,'0111485966','8956 nabil faker st');
INSERT INTO `customers` VALUES (4,'khaled','nasser',57,'01252546959','30 SLK companies');
INSERT INTO `customers` VALUES (5,'mohamed','kamal',44,'0125285695','147 banha st');
INSERT INTO `customers` VALUES (6,'shady','mohamed',32,'01010252682','785 salem eldoky st');
INSERT INTO `customers` VALUES (7,'kamal','khaled',26,null,'5088 ms3od Crossing');



CREATE TABLE `order_statuses` (
  `order_status_id` tinyint(4) NOT NULL,
  `name` varchar(50) NOT NULL,
  PRIMARY KEY (`order_status_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
INSERT INTO `order_statuses` VALUES (1,'home delivery');
INSERT INTO `order_statuses` VALUES (2,'inplace buying');


CREATE TABLE `orders` (
  `order_id` int(11) NOT NULL AUTO_INCREMENT,
  `customer_id` int(11) NOT NULL,
  `order_date` date NOT NULL,
  `status` tinyint(4) NOT NULL DEFAULT '1',
  `shipped_date` date DEFAULT NULL,
  `staff_id` smallint(6) DEFAULT NULL,
  PRIMARY KEY (`order_id`),
  KEY `fk_orders_customers_idx` (`customer_id`),
  KEY `fk_orders_staff_idx` (`staff_id`),
  KEY `fk_orders_order_statuses_idx` (`status`),
  CONSTRAINT `fk_orders_customers` FOREIGN KEY (`customer_id`) REFERENCES `customers` (`customer_id`) ON UPDATE CASCADE,
  CONSTRAINT `fk_orders_order_statuses` FOREIGN KEY (`status`) REFERENCES `order_statuses` (`order_status_id`) ON UPDATE CASCADE,
  CONSTRAINT `fk_orders_staff` FOREIGN KEY (`staff_id`) REFERENCES `staff` (`staff_id`) ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
INSERT INTO `orders` VALUES (1,4,'2019-02-03',1,'2019-02-04',3);
INSERT INTO `orders` VALUES (2,5,'2019-05-12',2,'2019-05-14',4);
INSERT INTO `orders` VALUES (3,2,'2019-12-14',1,'2019-12-16',3);
INSERT INTO `orders` VALUES (4,6,'2020-05-11',1,'2020-05-12',3);
INSERT INTO `orders` VALUES (5,1,'2019-07-21',2,'2019-07-21',3);
INSERT INTO `orders` VALUES (6,7,'2019-10-20',1,'2019-10-22',4);
INSERT INTO `orders` VALUES (7,3,'2019-11-11',2,'2019-11-14',4);
INSERT INTO `orders` VALUES (8,4,'2020-04-02',1,'2020-04-09',3);
INSERT INTO `orders` VALUES (9,5,'2019-01-05',2,'2019-01-05',3);
INSERT INTO `orders` VALUES (10,2,'2019-11-02',2,'2019-11-03',4);

CREATE TABLE `order_items` (
  `order_id` int(11) NOT NULL AUTO_INCREMENT,
  `book_id` int(11) NOT NULL,
  `quantity` int(11) NOT NULL,
  PRIMARY KEY (`order_id`,`book_id`),
  KEY `fk_order_items_books_idx` (`book_id`),
  CONSTRAINT `fk_order_items_orders` FOREIGN KEY (`order_id`) REFERENCES `orders` (`order_id`) ON UPDATE CASCADE,
  CONSTRAINT `fk_order_items_books` FOREIGN KEY (`book_id`) REFERENCES `books` (`book_id`) ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
INSERT INTO `order_items` VALUES (1,4,4);
INSERT INTO `order_items` VALUES (2,1,2);
INSERT INTO `order_items` VALUES (6,4,4);
INSERT INTO `order_items` VALUES (8,2,2);
INSERT INTO `order_items` VALUES (4,4,10);
