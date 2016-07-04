# HTTPong for AngularJS

Add this to your code:

```javascript
app.run(['$http', '$document', function($http, $document) {
  $document.ready(function() {
    HTTPong.initialize();
    HTTPong.getScheme('animal-farm').setApiUrl('/api/v1');
  });
  return HTTPong.setHttpFunction($http);
}]);
```

Then just use HTTPong in your controller, or create a factory that returns your scheme.

```javascript
app.factory('Scheme', [function(){
  return HTTPong.getScheme('animal-farm');
}]);
```
