
### 🔐 1. BOLA (Broken Object Level Authorization)

#### 🔎 Challenge 1: Access details of another user’s vehicle
- **Objective:** Leak sensitive information of another user's vehicle.
- **Tip:** Vehicle IDs are GUIDs — find a way to expose other users’ vehicle IDs.
- Look for an endpoint like `/api/location-service/vehicle/{id}/location`.


After successfully logging into the crAPI application , a platform designed to manage vehicles, we came across a feature labeled "Refresh Location" . This feature is used to update the current location of an owned vehicle.
![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Object%20Level%20Authorization/get_location.png?raw=true)


By analyzing the backend API requests, we identified an endpoint responsible for retrieving vehicle location data. This endpoint includes the vehicle ID as a parameter in the request URL, making it a potential target

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Object%20Level%20Authorization/author_id.png?raw=true)

While exploring the application, we came across a feature that allows users to create posts and leave comments .

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Object%20Level%20Authorization/add_comment.png?raw=true)

After posting a comment, we observed that the API endpoint returned sensitive information about the author of the post, including their email address and vehicle ID .

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Object%20Level%20Authorization/author_id.png?raw=true)

As previously observed, the refresh location API request requires a vehicle ID as a parameter. By using the leaked vehicle ID obtained from the victim's post comment response, we were able to successfully retrieve the real-time location of their vehicle.

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Object%20Level%20Authorization/car_location_leaked.png?raw=true)
---




#### 🔎 Challenge 2: Access mechanic reports of other users
- **Objective:** Access mechanic reports submitted by other users.
- Steps:
  - Analyze the report submission process.
  - Find a hidden API endpoint that exposes mechanic reports.
  - Modify the report ID to access others' reports.

 
 Within the application, there is a feature that allows users to contact a mechanic and submit complaints or feedback regarding vehicle services. This functionality interacts with an API endpoint that handles user-submitted reports.

 ![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Object%20Level%20Authorization/contact_mechanic.png?raw=true)

 After submitting a complaint to the mechanic through the application, the API endpoint returned a generated report link that allowed access to the submitted report.

 ![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Object%20Level%20Authorization/contact_mechanic_post.png?raw=true)

As observed in the generated report URL, the API includes a parameter named report_id. By modifying this value and resending the request, we were able to access reports belonging to other users. This allowed us to retrieve sensitive personal information , including the mechanic’s name and address , the victim’s car VIN (Vehicle Identification Number) , and their home address and phone number .


![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Object%20Level%20Authorization/vehicule_vin_leaked.png?raw=true)



 This confirms a critical Broken Object Level Authorization (BOLA) vulnerability, where an attacker can exploit exposed object identifiers to access private user data without proper authorization.




