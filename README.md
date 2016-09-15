# WIP - IndexedDB Examples

*Examples of how to use IndexedDB*

### Support

<p align="center">![]('IndexedDB')</p>

[Full specs](https://www.w3.org/TR/IndexedDB/)

### API


#### Open Database Connection

```js
var dbRequest = indexedDB.open("myDatabase", 1);
```

To open an database, just use ```open``` method with database name. Second argument is version of database.

##### Tips

```js
var db1Request = indexedDB.open("myDatabase1", 1.5);
```

In above example, 1.5 version will be rounded to 1. So use whole number instead of decimal for DB version.

#### Events

```js
db.onerror = function(event) {
  //On error event
};
```

```js
db.onsuccess = function(event) {
  //On success event
};
```

#### To handle generic error for particular DB

```js
var db;

dbRequest.onsuccess = function(event) {
  //On success event
  db = event.target.result; //DB v1 error
};

//Handle error for above DB only
db.onerror = function(event) {
  console.log("Error Code: ", event.target.errorCode);
}
```



### Wrapper Libraries

- [localForage](https://localforage.github.io/localForage/)

- [pouchdb](https://pouchdb.com/)

- [dexie](http://dexie.org/)


#### Reference

- [MDN](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API/Using_IndexedDB)

- [IndexedDB](https://gist.github.com/BigstickCarpet/a0d6389a5d0e3a24814b)



##### MIT Licensed
