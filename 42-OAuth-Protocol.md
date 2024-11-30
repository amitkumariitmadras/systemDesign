### **Authorization Across Distributed Systems: The OAuth Protocol**

**1. What is OAuth?**
- **OAuth** (Open Authorization) is an open standard for **access delegation**.
- It allows **third-party applications** to access a user’s resources without sharing credentials (username/password).

**2. OAuth Flow (Basic Process)**
- **Authorization Request**: The client requests authorization from the user (via the Authorization Server).
- **Authorization Grant**: The user grants permission.
- **Access Token**: The Authorization Server issues an access token to the client.
- **Access Resource**: The client uses the access token to access the user’s resources from the Resource Server.

**3. OAuth Roles**
- **Resource Owner**: User who owns the data.
- **Client**: Application that wants to access the resource.
- **Authorization Server**: Authenticates the user and provides access tokens.
- **Resource Server**: Hosts the user’s resources (e.g., APIs).

**4. OAuth Grant Types**
- **Authorization Code**: For web apps. The most secure type.
- **Implicit**: For client-side apps (less secure).
- **Password Credentials**: Direct login (used by trusted apps).
- **Client Credentials**: For app-to-app authentication.

**5. Example OAuth 2.0 Flow**
1. **User** grants permissions.
2. **Authorization Server** issues an **Authorization Code**.
3. **Client** exchanges it for an **Access Token**.
4. **Client** uses the **Access Token** to access protected resources from the **Resource Server**.

```python
# Example using OAuth 2.0 with Python (requests library)

import requests

# Request token from the Authorization Server
response = requests.post('https://authorization-server.com/token', data={
    'grant_type': 'authorization_code',
    'code': 'authorization_code',
    'redirect_uri': 'redirect_uri',
    'client_id': 'client_id',
    'client_secret': 'client_secret',
})

# Access the resource with the Access Token
access_token = response.json()['access_token']
resource_response = requests.get('https://api.resource-server.com/data', headers={
    'Authorization': f'Bearer {access_token}'
})
print(resource_response.json())
```

**6. Advantages of OAuth**
- **Security**: Credentials are never shared with third-party apps.
- **Granular access**: Specific permissions (scope) can be granted (e.g., read-only).
- **Token expiration**: Access tokens have limited lifetimes, improving security.

**7. OAuth vs. Traditional Authentication**
- Traditional: Credentials sent directly to the server.
- OAuth: Tokens are exchanged, credentials never leave the user's device.

**8. Visualizing OAuth Flow**
```
[User] --(1)--> [Authorization Server] --(2)--> [Client]
   ^                                      |
   |---- (3)----> [Resource Server] <-----|
```

**Summary:**
- OAuth enables secure, token-based **authorization** for accessing resources.
- It's commonly used in **API authentication**, enabling third-party services like Google, Facebook to grant access without exposing passwords. 

