# create-random-test

## Back-End: Lumen 5.8
- Stateless Restful API
- Authentication & authorization by JWT middleware
- Micro-services  architecture
- Eloquent ORM
- Database schema & migration
- Mysql (PDO) Database
- Validate incoming data
- Seeding input data by model factories
- Logging by Illuminate\Support\Facades\Log
## API Documentation
### `POST` /login
#### Parameter:
Parameter | Description
--------- | -----------
phone-number* | without ziro. example: '9164210427'
password* | at least 6 characters

#### Reponses:
- `200` Succeeded:
```javascript
{
    "ok": true,
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJyZXN0ZnVsLWFwaS1sdW1lbiIsInN1YiI6ODEsImlhdCI6MTU1Mjg2MjA5OCwiZXhwIjoxNTUyODY1Njk4fQ.Y2ZajmVy2cFEJZyruP_Ewnf5U4V75MzlUkztAD25y3c"
}
```
- `400` Params doesn't valid:
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

- `400` Phone number not registered:
```javascript
{
    "ok": false,
    "error": {
        "type": "NOT_REGISTERED",
        "message": "This phone number is not registered yet"
    }
}
```

- `400` The password does not match the username:
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

- `400` The password does not match the username:
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
