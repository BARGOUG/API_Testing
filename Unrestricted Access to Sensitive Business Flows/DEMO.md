In the shop menu, we noticed that items such as a wheel are available for purchase at a price of $10.
![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Unrestricted%20Access%20to%20Sensitive%20Business%20Flows/images/Screenshot%202025-06-08%20151104.png?raw=true)


Clicking the 'Buy' button triggers a request that includes the product_id and quantity as input parameters.


![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Unrestricted%20Access%20to%20Sensitive%20Business%20Flows/images/Screenshot%202025-06-08%20151249.png?raw=true)

Following the observed logic, purchasing one item (quantity of 1) deducts $10 from the balance. Therefore, buying 10 units should deduct $100. However, when we experimented with entering a negative quantity , such as -100, the system processed the request and instead added $1000 to our balance .

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Unrestricted%20Access%20to%20Sensitive%20Business%20Flows/images/Screenshot%202025-06-08%20151451.png?raw=true)


This demonstrates a business logic flaw in the application — specifically, the system fails to properly validate input values (like quantity), allowing users to manipulate the purchase process in unintended ways. Entering a negative number should either be blocked or handled correctly by the system, not used to increase a user's balance fraudulently.
