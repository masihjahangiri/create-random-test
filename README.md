# create-random-test
## API Documentation
### /auth/login
#### Parameter:
Parameter | Description
--------- | -----------
phone-number* | without ziro. example: '9164210427'
password* | at least 6 characters

#### Reponses:
- Succeeded:
```javascript
{
    "ok": true,
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJyZXN0ZnVsLWFwaS1sdW1lbiIsInN1YiI6ODEsImlhdCI6MTU1Mjg2MjA5OCwiZXhwIjoxNTUyODY1Njk4fQ.Y2ZajmVy2cFEJZyruP_Ewnf5U4V75MzlUkztAD25y3c"
}
```
- Params doesn't valid:
```javascript
{
    "ok": false,
    "error": {
        "type": "INVALID_PARAM",
        "message": "Some parameters are not valid",
        "invalidParams": [
            "phone-number"
        ]
    }
}
```

- Phone number not registered:
```javascript
{
    "ok": false,
    "error": {
        "type": "NOT_REGISTERED",
        "message": "This phone number is not registered yet"
    }
}
```

- The password does not match the username:
```javascript
{
    "ok": false,
    "error": {
        "type": "INCORRECT_PARAM",
        "incorrectParam": [
            "phone-number",
            "password"
        ],
        "message": "Phone number or password is incorrect"
    }
}
```

- The password does not match the username:
```javascript
{
    "ok": false,
    "error": {
        "type": "INCORRECT_PARAM",
        "incorrectParam": [
            "phone-number",
            "password"
        ],
        "message": "Phone number or password is incorrect"
    }
}
```
