
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

---




#### 🔎 Challenge 2: Access mechanic reports of other users
- **Objective:** Access mechanic reports submitted by other users.
- Steps:
  - Analyze the report submission process.
  - Find a hidden API endpoint that exposes mechanic reports.
  - Modify the report ID to access others' reports.

