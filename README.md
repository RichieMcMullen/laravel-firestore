# Laravel Firestore

The Google firestore wrapper for Laravel.

## Requirement

* Laravel 5.8.*
* [gRPC extension](https://cloud.google.com/php/grpc)

## Install
```shell
composer require vohinc/laravel-firestore
```

## Publish Configuration
```shell
php artisan vendor:publish --provider=Voh\LaravelFirestore\FirestoreServiceProvider --tag=config
```

## Usage


#### Add to Controller
```php
use Voh\LaravelFirestore\Facades\Firestore;
```


#### Store Data
```php
Firestore::collection('users')->document('lovelace')->set([
    'first' => 'Ada',
    'last' => 'Lovelace',
    'born' => 1815,
]);
```


#### Retrieve All Documents within a Collection
```php
$firestore = Firestore::collection('users');
$documents = $firestore->documents()->rows();
foreach($documents as $key => $document)
{
    // Handle data
    $document->.....
}
```
