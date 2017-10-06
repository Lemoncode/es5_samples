## 3. Arguments

# We can feed 0 or multiple parameters to a function. If we do a reference to parameters that are not feed we are going to have an undefined for that parameter. The interesting thing is that functions in javascript has a property that is a container for all the parameters that are feed it. 

### Steps.


#### 1. Lets access to the arguments.

```diff
+(function () {
+  var showMyArgs = function () {
+    if(arguments.length > 0) {
+      for (var i = 0; i < arguments.length; i++) {
+        console.log(arguments[i]);
+      }
+    } else {
+      console.log('No arguments provided');
+    }
+  };
+})();
```

#### 2. Now with this on place let's call this function with different parameters

```diff
(function () {
  var showMyArgs = function () {
    if(arguments.length > 0) {
      for (var i = 0; i < arguments.length; i++) {
        console.log(arguments[i]);
      }
    } else {
      console.log('No arguments provided');
    }
  };
+  showMyArgs();
+  showMyArgs('pepe', 34, { description: 'Jaim' }, [2, 'a', 89.09]);
})();
```
