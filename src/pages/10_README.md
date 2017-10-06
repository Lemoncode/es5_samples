## 8. Prototype pattern.

### Steps.

#### 1. Let's first define a name space.

```diff
+var App = App || {};
```
* This is going to be loaded on the global scope. But under this 'namespace', our definitions will be host, just to avoid the colission of names, betweeen loaded functionalities.

#### 2. Now let's refactor our previous prototype code to implement the reveal module pattern.

```diff
+var App = App || {};

+(function (App){
+  App.Car = function (engine, price) {
+    var started = false;
+
+    var start = function () {
+      if(!started) {
+        console.log('car started engine: ' + engine);
+      }
+      started = true;
+    };
+
+    var stop = function () {
+      if(started) {
+        console.log('car stoped engine: ' + engine);
+      }
+      started = false;
+    };
+
+    return {
+      engine: engine,
+      price: price,
+      start: start,
+      stop: stop
+    };
+  };
+})(App);
```

#### 3. Now let's add some code to watch how this is working. 
 
```diff
...
+var car1 = App.Car('V12', 3453453543);
+var car2 = App.Car('V8', 64773647);
+
+car1.start();
+car1.start();
+car2.stop();
+car2.start();
```
