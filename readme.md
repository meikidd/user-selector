# user selector
this is a webcomponent for selecting users

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
### Load remote data
- use `data-url` attribute. When you set `data-url` attribute, user-selector will launch Ajax request `http://example.com/users/search?keyword={keyword}` to the server to get the JSON data.

```html
<user-selector data-url="//example.com/users/search">
  <input type="text" placeholder="input username here" />
</user-selector>
```

## Events

### selected


### remove
