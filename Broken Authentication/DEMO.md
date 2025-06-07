# Broken User Authentication Challenge

## Overview

This repository contains resources and solutions for the "Broken User Authentication" challenge from crAPI. The goal is to reset the password of a different user by exploiting vulnerabilities in the authentication mechanism.

---

## Challenge Details

### Challenge 3 - Reset the password of a different user

- **Objective**: Find an email address of another user on crAPI and reset their password.
- **Approach**:
  - **Find an email address**: Identify the email address of another user. This might involve enumerating users or using other vulnerabilities.
  - **Brute forcing**: If protection mechanisms are in place (e.g., rate limiting), consider leveraging the predictable nature of REST APIs to find more similar API endpoints.

For this demo we created two seperate accounts 'hamza' & 'yessine' with different passwords and mails

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Authentication/images/accs.png?raw=true)

So then, as the user Hamza , we created a post.

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Authentication/images/create_post.png?raw=true)

As the user Yessine, we commented on Hamza's post and noticed that the endpoint returned the author's email address, indicating a potential vulnerability.

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Authentication/images/leaked_email.png?raw=true)


We then clicked on the "Forgot Password" feature in an attempt to reset Hamza's password. The application responded by sending an OTP — a 4-digit verification code — to confirm whether Hamza was the one who initiated the password reset request.

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Authentication/images/forget_password_interface.png?raw=true)

![image alt](https://github.com/BARGOUG/API_Testing/blob/main/Broken%20Authentication/images/forget_password_request.png?raw=true)





