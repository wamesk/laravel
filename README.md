# Package for core utilities to be used in multiple packages

## Installation

```bash
composer require wamesk/laravel
```

## Usage

### ExceptionHandler

When using `wamesk/laravel`  package or `WameException` exception you need to register this `ExceptionHandler`.

```php
// bootstrap/app.php

->withExceptions(function (Exceptions $exceptions) {
    ...
    $exceptions->render(resolve(ExceptionHandler::class));
    ...
})->create();
```

### WameException

Was created to be used with `ExceptionHandler` for custom frontend response, can be used anywhere in project.
Code in WameException will be used as status code.
Message will be used as code and will be put in translator `__($exception->getMessage())` for message.

Response example

```json
{
    "code": "1.1",
    "message": "Error message"
}
```
