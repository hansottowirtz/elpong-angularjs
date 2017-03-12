# Elpong for AngularJS

There is no need for a separate angularjs module, as support for `$http` is built-in.

Add this to your code:

```javascript
app.config([function(){
  Elpong.enableAutoload(); // when using preloading
}]);
app.run(['$http', function($http){
  Elpong.setAjax($http);
}]);
```

Make sure your preloaded meta tags come before the script that loads angularjs.

Then just use Elpong in your controller, or create a factory that returns your scheme.

```javascript
app.factory('Elpong', ['$window', function($window){
  return $window.Elpong;
}]);
app.factory('Scheme', ['Elpong', function(Elpong){
  var scheme = Elpong.get('animal-farm');
  scheme.setApiUrl('/api');
  return scheme;
}]);
```
