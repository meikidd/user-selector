# user selector
this is a webcomponent for selecting users

## Install
```
npm install user-selector
```

## Integrating with your Application
```
<link rel="import" href="./user-selector.html">
```

```
<user-selector data-users='[{"id":"1","name":"Qingguang Mei","lastName":"Mei"},{"id":"3","name":"Ying Cheng","lastName":"Cheng"},{"id":"4","name":"Qianhe Mei","lastName":"Mei"}]'>
  <input type="text" placeholder="input username here" />
</user-selector>
```

### Set user data
- use `data-users` attribute

```
<user-selector data-users='[{"id":"1","name":"Qingguang Mei","lastName":"Mei"},{"id":"3","name":"Ying Cheng","lastName":"Cheng"},{"id":"4","name":"Qianhe Mei","lastName":"Mei"}]'>
  <input type="text" placeholder="input username here" />
</user-selector>
```
- use `setUsers()` method

```
<user-selector>
  <input type="text" placeholder="input username here" />
</user-selector>
```

```
var users = [
	{"id":"1","name":"Qingguang Mei","lastName":"Mei"},
	{"id":"2","name":"Ying Cheng","lastName":"Cheng"},
	{"id":"3","name":"Qianhe Mei","lastName":"Mei"}
];

var userSelector = document.querySelector('user-selector');
userSelector.setUsers(users);
```

### Get selected user
```
var userSelector = document.querySelector('user-selector');
console.log(userSelector.value); // [{"id":1,"name":"Qingguang Mei","lastName":"Mei"}]
```


### Load remote data
- use `data-url` attribute. When you set `data-url` attribute, user-selector will launch Ajax request `http://example.com/users/search?keyword={keyword}` to the server to get the JSON data.

```
<user-selector data-url="//example.com/users/search">
  <input type="text" placeholder="input username here" />
</user-selector>
```