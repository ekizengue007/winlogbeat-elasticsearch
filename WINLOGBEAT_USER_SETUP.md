It is recommended to create a new user for Winlogbeat instead of using the `elastic` user for the following reasons:
1. **Least Privilege**: The `elastic` user is a superuser with broad permissions. Creating a dedicated user with restricted permissions reduces security risks in case of a compromise.
2. **Role Segregation**: Separating roles prevents a single user from having excessive powers, enhancing security.
3. **Tracking and Auditing**: Separate users make it easier to monitor and audit the specific activities of Winlogbeat.
4. **Security Management**: Using the `elastic` user in various parts increases the risk of credential exposure. A dedicated user reduces the impact of potential leaks.

Creating the Role
![image](https://github.com/user-attachments/assets/066f3100-e02f-40e5-9417-1fb282817261)

Creating the user
![image](https://github.com/user-attachments/assets/d831aaf0-98c0-442e-8e13-588174e6c099)

Creating the API Key
1. Go to dev tools
![image](https://github.com/user-attachments/assets/712da44e-ca20-440b-8e74-f1f3c56223f3)
2. Past the code:
   POST /_security/api_key/grant
{
  "grant_type": "password", 
  "username": "ingest_winlogbeat",
  "password": "YourPassword",
  "api_key" :  {
"name": "the_api_name"
}
  
}

3. you can use the combination of "id:api_key" apykey or simply user the "encoded" value
