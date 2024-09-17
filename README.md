[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/r-tQZu0l)
# BBT3104-Lab1of6-DatabaseTransactions


| **Key**                                                               | Value                                                                                                                                                                              |
|---------------|---------------------------------------------------------|
| **Group Name**                                                               | B8 |
| **Semester Duration**                                                 | 19<sup>th</sup> August - 25<sup>th</sup> November 2024                                                                                                                       |

## Flowchart
![alt text](image.png)

## Pseudocode
1.specify the database
2.start the transaction
3.calculate the latest order-number
5.create a save-point before inserting a fisrt product
6.insert the first product
7.create a save point before inserting the next data
8.insert the second porduct and update its quantity in the stock
9.create the third save point
10.recieve the payments made by the customer
11.commit
12.confirm the effect of the committed transaction


## Support for the Sales Departments' Report
To enable tracking of unpaid orders and generate a report on the balance remaining for each order, you can improve the database design by adding:
1.A payments table to store all payments details for each order.
2.Add a calculated field that will automatically update the remaining balance after each payment recorded.
3.Add a payments field in the orders table to track the payments status of ech order.(eg. partially paid or "paid in full" or unpaid)
4.Ensure the system logs each payment anf the balance after each transaction.
5.write an SQL querie that joins the orders and payments table to generate reports for orders that are not fully paid.
By adding a payments table, tracking balances, and providing     payment status fields, the sales department can easily generate reports on outstanding balances and follow up with clients efficiently.
