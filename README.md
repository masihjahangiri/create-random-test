# create-random-test
## Stack and Architecture
- Micro-service
- Docker & docker-compose
- Docker and docker-compose or docker swrm
- Web Server:
    - Nginx: static server and reverse proxy server
    - Gzip compressor
    - OS: debian:stretch-slim
- Backend: 
    - Lumen: Micro-services architecture
    - Stateless Restful API
    - Standard: White House Web API
    - Authentication & authorization by JWT middleware
    - Moloquent ORM
    - Database schema & migration
    - Database: NoSQL (mongoDB)
    - Validate incoming data
    - Seeding input data by model factories
    - Excel reader: phpoffice/phpspreadsheet:1.4
    - Image Processing: sybio/image-workshop:2.1
    - Zip archive reader: nelexa/zip:3.1
    - Logging by Illuminate\Support\Facades\Log
    - PHP-FPM
    - OS: alpine:3.9
- Database:
    - NoSQL - mongoDB
    - all query is lean
    - Driver: jenssegers
    - OS: ubuntu:xenial
- Frontend:
    - SPA
    - Programing architecture: FP - event driven
    - Mathematics display engine: Mathjax
    - Live Render Latex and Mathjax
    - Layout: Flexbox

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
