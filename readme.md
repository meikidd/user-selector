# user selector
this is a webcomponent for selecting users. [demo](http://meikidd.github.io/user-selector/demo.html)


## Install
```
npm install user-selector
```

## Integrating with your Application
```html
<link rel="import" href="./user-selector.html">
```

```html
<user-selector data-users='[{"id":"1","name":"Qingguang Mei","lastName":"Mei"},{"id":"3","name":"Ying Cheng","lastName":"Cheng"},{"id":"4","name":"Qianhe Mei","lastName":"Mei"}]'>
  <input type="text" placeholder="input username here" />
</user-selector>
```

### Get selected users

```js
var userSelector = document.querySelector('user-selector');
console.log(userSelector.value); // [{"id":1,"name":"Qingguang Mei","lastName":"Mei"}]
```

### Set selected users
```js
var userSelector = document.querySelector('user-selector');
userSelector.setSelected([{id:12,name:'qingguang',nickname:'meikidd'}]);
```

### Set data users
You can use `setUsers(data)` to set user data.
```js
var userSelector = document.querySelector('user-selector');
userSelector.setUsers([{id:12,name:'qingguang',nickname:'meikidd'}]);
```
or attribute `data-users`
```
<user-selector data-users='[{"id":"1","name":"Qingguang Mei","lastName":"Mei"},{"id":"3","name":"Ying Cheng","lastName":"Cheng"},{"id":"4","name":"Qianhe Mei","lastName":"Mei"}]'>
  <input type="text" placeholder="input username here" />
</user-selector>
```

### Set template
Customize search list item format by `setTemplate`
```js
var userSelector = document.querySelector('user-selector');
userSelector.setTemplate('{name} ({nickname}) - {id}');
```
or attribute `data-template`
```
<user-selector data-template='{name} ({nickname}) - {id}'>
  <input type="text" placeholder="input username here" />
</user-selector>
```

### Load remote data
- use `data-url` attribute. When you set `data-url` attribute, user-selector will launch Ajax request `http://example.com/users/search?keyword={keyword}` to the server to get the JSON data.

```html
<user-selector data-url="//example.com/users/search">
  <input type="text" placeholder="input username here" />
</user-selector>
```

## Events

### select
triggered when a user been selected
```
var userSelector = document.querySelector('user-selector');
userSelector.addEventListener('select', function(e) {
  console.log(e.data.user);
});
```

### remove
triggered when a user been removed
```
var userSelector = document.querySelector('user-selector');
userSelector.addEventListener('remove', function(e) {
  console.log(e.data.user);
});
```