---
layout: post
title: "Data Modelling Reflection"
author:
- Jacob Collier-Tenison
---
In order to model the date, I made the following assumptions:
- Each customer will create an account under a unique phone number
This allows the phone number to be used as a primary key, but would not allow customers who share a number (such as a home phone) to have their own accounts under that number.
- An employee of the grocery store will fufill each order by hand
This meant that I needed to include emplyess in the database so that they could be assigned to fufill an order. 
- Each employee is assigned a unique ID
This allowed me to use the employee id as a unique identifier for the employees
- The final price will be determined when the order is fuffiled to allow for any substitutions or out of stock items
This mean that the final price would not be attached to the order itself, but to the fuffillment of that order, since it is subject to the in-store availability which could differ from that on the website due to customers in the store. 
- A customer will pay using the store's normal methods, not online
This means that no payment method is needed in the database
- A unique order number will be generated for each order
Doing this allows that number to be used as the primary key for the order

With these assumptions in mind, I put together the following Entity-Relationship diagram. 
![ER]({{"/assets/img/GroceryER.png"|relative_url}})
I chose to respresent customers, orders, items, and employees as entities. Based on the prompt, it was obvious that both customers and items needed to be entities in this model because they both had many attributes and there would be many of them in the system. In addition, I chose to include orders as en entitied becuase I thought of the scenario as customers placing whole orders that contained items, not customers ordering individual items. This is realistic to how a grocery store would look at this order because they would need to collect all of the items together for the customer to pick up at the specific order date and time. I also included emplyees based on my assumption for how orders would be fufilled. As far as relationships go, I said that customers place orders because they are the ones who input that into the system. I also said at orders contains items because a order is essentially made up of or or more items. In addition, this relationship has several attributes to provide more information for the item in the specific order (quantity, instructions, and replacements). Finally, I said that emplyees fufill orders, with this relationship containing the price that would be determined while the order is fulfilled. 

After my ER diagram was complete, I created an SQL Schema.
![SQL]({{"/assets/img/GrocerySQL.png"|relative_url}})
To begin, I created each entity as a table and added its attributes as columns. Then, I arranged them in the way I thought they should be connected and thought about what was missing. By doing this, I determined that I needed to add a contains table to keep track of the items and details of items contained in each order and a fuffiledorders table that would connect an order to an employee and store the final price. From there I decided the PK of each table, which is when I had to make many of the assumptions that I have already listed above. For the two tables that I added, I used the Pks of the things they connected as their PKs since they do not exist indepentdently of those things. 

Overall, I am satisified with my representation of all the information. I feel that it is realistic to the way grocery store ordering operates. I also think that it thoroughly considers the relationship between each component of the ordering process. However, that does not mean that implementing it would not bring its own challenges. Some of these would be frustration from customers who do not know the final price until pickup, ensuring that phone numbers are recorded properly as integers, determining how employees would be assigned to orders, making sure that the stock listed online matches that in the store, and creating an interface that allows customers to add items to their order with attributes from contains. 