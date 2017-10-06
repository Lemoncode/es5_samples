## 8. Prototype pattern.

### Steps.

#### 1. Let's first define a name space.

```diff
+var App = App || {};
```
* This is going to be loaded on the global scope. But under this 'namespace', our definitions will be host, just to avoid the colission of names, betweeen loaded functionalities.

#### 2. Now we are going to describe the container for our 'class'.

```diff
+(function (App) { 
+  
+})(App);
```
* If we pause debugger now we can watch that there are two  scopes local and window
* This way we avoid pollute the global scope.

#### 3. Let's create our constructor.

```diff
....
(function (App) {
+  App.Car = function(engine, price) {
+    this.engine = engine;
+    this.price = price;
+  };
})(App);
```

#### 4. Let's create a couple of methods.

```diff
(function (App) {
  App.Car = function(engine, price) {
    this.engine = engine;
    this.price = price;
  };
  
+  App.Car.prototype = {
+    start: function () {
+      console.log('Car with engine' + this.engine +'started');
+    },
+    stop: function () {
+      console.log('Car with engine' + this.engine +'stopped');
+    }
+  };
})(App);
```

#### 5. Now let's create some instances of Car.

```diff
+(function (App) {
+  var car1 = new App.Car('V12', 345353);
+  var car2 = new App.Car('V8', 89489449);
+  car1.start();
+  car2.stop();
+  var car3 = App.Car('HJ', 1000);
+  console.log(car3);
+})(App);
```
* Watch wheree the __proto__ is pointing now.
