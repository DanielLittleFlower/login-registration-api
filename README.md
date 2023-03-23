# Laravel Login and Registration API
This is a server-side API built with Laravel that handles authentication and registration requests for a mobile application. The API is built to work with a Flutter-based mobile app that allows users to register an account and login. The app uses HTTP requests to communicate with this API for authentication and registration purposes.

The server-side API uses Laravel's built-in authentication system to handle user authentication and registration. The API uses JSON web tokens (JWT) for user authentication.

## Prerequisites
- PHP 7.4 or higher installed on your machine.
- Composer installed on your machine.
- Basic knowledge of Laravel PHP framework.

## Getting started

1. Clone the repository to your local machine

`git clone https://github.com/DanielLittleFlower/laravel-login-registration-api.git`

2. Open the project in your preferred code editor.
3. Run composer install to install the dependencies.
4. Create a new MySQL database and update the database credentials in the .env file.
5. Run the database migrations using php artisan migrate.
6. Start the development server using php artisan serve.


# API Endpoints
The following endpoints are available in the API:

## Register

_Endpoint_: `POST /api/register`

_Description_: Allows users to register an account.

_Request body_:

```
{
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password"
}
```

_Response body (successful registration)_:

```
{
    "status": "success",
    "message": "Account created successfully."
}
```

_Response body (registration failed)_:

```
{
    "status": "error",
    "message": "The given data was invalid.",
    "errors": {
        "email": [
            "The email has already been taken."
        ]
    }
}
```

## Login

_Endpoint_: `POST /api/login`

_Description_: Allows users to login to their account.

_Request body_:

```
{
    "email": "johndoe@example.com",
    "password": "password"
}
```

_Response body (successful login)_:

```
{
    "status": "success",
    "token": "<JWT token>"
}
```

_Response body (login failed)_:

```
{
    "status": "error",
    "message": "These credentials do not match our records."
}
```

## User Details

_Endpoint_: `GET /api/user`

_Description_: Returns the authenticated user's details.

__Headers__:

`Authorization: Bearer <JWT token>`

_Response body_:

```
{
    "id": 1,
    "name": "John Doe",
    "email": "johndoe@example.com",
    "email_verified_at": null,
    "created_at": "2023-03-22T12:34:56.000000Z",
    "updated_at": "2023-03-22T12:34:56.000000Z"
}
```

### Contributing
Contributions are welcome! If you would like to contribute to this project, please fork the repository and submit a pull request.

### License
This project is licensed under the MIT License.

For more information about the Flutter-based mobile application that works with this API, please refer to the [README](https://github.com/DanielLittleFlower/simple-login-registration-flutter-dart) file of the mobile app repository.