# BBT3104-Lab1of6-DatabaseTransactions


| **Key**                                                               | Value                                                                                                                                                                              |
|---------------|---------------------------------------------------------|
| **Group Name**                                                               | ? |
| **Semester Duration**                                                 | 19<sup>th</sup> August - 25<sup>th</sup> November 2024                                                                                                                       |

## Flowchart

## Pseudocode
1.specify the database
        USE classicmodels;
2.start the transaction
        START TRANSACTION;
3.calculate the latest order-number
        SET @orderNumber = (SELECT MAX(orderNumber)+1 FROM orders);
4.create a new order
        INSERT INTO orders(orderNumber,
        orderDate,
        requiredDate,
        shippedDate,
        status,
        customerNumber)

    VALUES(@orderNumber,
    DATE(NOW()),
    DATE(DATE_ADD(NOW(), INTERVAL 3 DAY)),
    DATE(DATE_ADD(NOW(), INTERVAL 2 DAY)),
    'In Process',
    145);
5.create a save-point before inserting a fisrt product
        SAVEPOINT before_product_1;
6.insert the first product
        INSERT INTO orderdetails(orderNumber, productCode, quantityOrdered, priceEach, orderLineNumber)
        VALUES(@orderNumber,'S18_1749', 2724, '136', 1);
7.create a save point before inserting the next data
SAVEPOINT before_product_2; 
8.insert the second porduct and update its quantity in the stock
        INSERT INTO orderdetails(orderNumber, productCode, quantityOrdered, priceEach, orderLineNumber)
        VALUES(@orderNumber,'S18_2248', 540, '55.09', 2);
9.create the third save point
        SAVEPOINT before_product_3;
10.recieve the payments made by the customer
        INSERT INTO payments
        (customerNumber, checkNumber, paymentDate, amount)
        VALUES (145, 'JM555210', DATE(NOW()), 300000);                
11.commit
COMMIT;
12.confirm the effect of the committed transaction
SELECT *
FROM
classicmodels.orderdetails
WHERE
orderNumber = 10426;
## Support for the Sales Departments' Report
