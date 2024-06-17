Hello!
Here is a link to my Tableau project.
https://public.tableau.com/app/profile/marina.mikhailova/viz/AdwentureWorksProject/Salesdashboard

For this dashboard I used AdventureWorks dataset Sales Order data that is located in my google account.
Link: 
https://docs.google.com/spreadsheets/d/1USCN2HdSb07gwpxbwceIc5xRIiEUiIrpKtMnPNdZtIk/edit?usp=sharing


I also additionally calculated Average profit by Customer using this query:
```
SELECT  so.SalesOrderID,so.ProductID, p.StandardCost, so.OrderQty, so.Linetotal
FROM `adwentureworks_db.product` p
JOIN `adwentureworks_db.salesorderdetail`so
ON so.ProductID = p.ProductID
GROUP BY 1,2,3,4,5
ORDER BY 2
```
and added that csv file to existing datasource. 

This dataset has some issues, so calculation of Avg Profit using Linetotal and StandardCost*OrderQty gave an unclear result.
So instead of that I used Subtotal and calculated Avg Sales per Customer.
