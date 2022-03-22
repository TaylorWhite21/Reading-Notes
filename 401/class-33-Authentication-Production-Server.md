# Authentication & Production Server

## Introduction to JSON Web Tokens

### What is JSON Web Token?
JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed.

### When should you use JSON Web Tokens?

Authorization: 
This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

#### Information Exchange: 
JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

### JWTs consist of three parts:
- Header
- Payload
- Signature

```
xxxxx.yyyyy.zzzzz
```

Header:
```
{
  "alg": "HS256",
  "typ": "JWT"
}
```

Payload:
```
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```

Signature:
```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
  ```

## How to use JWT

## Installation & Setup

For this tutorial we are going to use the djangorestframework_simplejwt library, recommended by the DRF developers.

### Install:
```
pip install djangorestframework_simplejwt
```

### settings.py
```
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

### urls.py
```
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```
