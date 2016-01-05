# webStorage.js [![Build Status](https://travis-ci.org/georapbox/webStorage.js.svg?branch=master)](https://travis-ci.org/georapbox/webStorage.js) [![Dependencies](https://david-dm.org/georapbox/webStorage.js.svg?theme=shields.io)](https://david-dm.org/georapbox/webStorage.js) [![devDependency Status](https://david-dm.org/georapbox/webStorage.js/dev-status.svg)](https://david-dm.org/georapbox/webStorage.js#info=devDependencies)

webStorage is a minimal Javascript library that improves the way you work with ```localStorage``` or ```sessionStorage```.


## Data API

The API methods below deal with getting and setting data in an offline store.

### getItem

```js
getItem(key)
```

Gets an item from an offline store. If the key does not exist, ```getItem()``` will return null.

### setItem

```js
setItem(key, value)
```

Saves an item to an offline store. You can store the following types of JavaScript objects:

- String
- Number
- Array
- Object

### removeItem

```js
removeItem(key)
```

Removes the value of a key from the offline store.

### clear

```js
clear([clearAll])
```

> Use this method with caution.

If ```clearAll``` is set to ```true```, removes every key from the storage, returning it to a blank slate.

If ```clearAll``` is set to ```false``` or any other falsy value it will remove only the keys that belong to the specific databse.

### keys

```js
keys()
```

Gets the list of all keys in the offline storage for a specific database.
If the ```name``` property is not set or set to ```''``` (empty string), returns all keys in storage.

### length

```js
length()
```

Gets the number of keys in the datastore.

### iterate

```js
iterate(iteratorCallback)
```

Iterate over all value/key pairs in datastore.

```iteratorCallback``` is called once for each pair, with the following arguments:
- key
- value


## Settings API

### config

```js
config(options)
```

Set and persist webStorage options. This must be called before any other calls to webStorage are made. The following options can be set:

##### driver
> The preferred driver to use. Use one between ```localStorage``` and ```sessionStorage```.<br>
Default: ```localStorage```

##### name
> The name of the database. This is used as prefix for all keys stored in the offline storage.<br>
Default: ```"webStorage"```


### createInstance

```js
createInstance([options])
```

Creates a new instance of the webStorage. The ```options``` are the same as ```config(options)```.


## Build the project

### 1. Install dependancies

```sh
cd webStorage.js
$ npm install
```

### 2. Build

```sh
$ npm run build
```

The command above will create a ```dist/``` folder that contains the library to be used in production. It will also lint the code and run the tests.
