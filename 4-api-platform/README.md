### Récupérer token jwt-auth

- .../api/login method POST dans le body au format JSON : 
``` 
 {
  "email": "<YOUR_MAIL>",
  "password": "<YOUR_PASSWORD>"
  } 
  ```
- retourne un token 
- .../api/tasks (ou autres routes protect par jwt) method GET/POST/PUT/DELETE etc... ajouter dans le header (key : Authorization, value : Bearer <JWT_TOKEN_GENERATE> 