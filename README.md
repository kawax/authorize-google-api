# Authorize HTTP Client Manager: Google API Driver

- https://github.com/kawax/authorize-manager
- https://github.com/google/google-api-php-client

## Requirements
- PHP >= 7.2
- Laravel >= 5.8

## Installation

```
composer require revolution/authorize-google-api
```

## Usage
```php
    $credentials = [
        'application_name' => '',
        'client_id'        => '',
        'client_secret'    => '',
        'redirect_uri'     => '',
        'scopes'           => [\Google_Service_PhotosLibrary::PHOTOSLIBRARY],
        'access_type'      => 'online',
        'approval_prompt'  => 'auto',
        'prompt'           => 'consent',
    ];

    if (Authorize::driver('google-api')->login($credentials)) {
        /**
         * @var \Google_Client $client
         */
        $client = Authorize::driver('google-api')->client();
        $client->setAccessToken($token);
        $photos = new \Google_Service_PhotosLibrary($client);
    }
```

## LICENSE
MIT  
Copyright kawax
