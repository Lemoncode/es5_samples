## 6. Closure

# Now let's talk about closures. Basically a closure, is a latch around a variable, what this means, is that when we have a inner function, if it has a reference to a variable that is in an outer function, it has access to to it even when we return the function.

### Steps

#### 1. Let's see how is the structure of a closure

```diff
+(function () {
+   var Time = function () {
+       var date = new Date();
+
+       var getLockedTime = function () {
+           return date.getTime();
+       };
+
+       return {
+           getLockedTime: getLockedTime,
+           getCurrentTime: function () {
+               var date = new Date();
+               return date.getTime();
+           }
+       };
+   };
+})();
```

#### 2. Now let's create a new Time instance, and what happen when we call getCurrentTime a couple of times.

```diff
(function () {
   var Time = function () {
       var date = new Date();

       var getLockedTime = function () {
           return date.getTime();
       };

       return {
           getLockedTime: getLockedTime,
           getCurrentTime: function () {
               var date = new Date();
               return date.getTime();
           }
       };
   };

+   var print = function (arg) {
+       console.log(arg);
+   };

+   var time = Time();

+   print(time.getCurrentTime());
+   print(time.getCurrentTime());
})();
```
* We can notice that each time the timestamp is different.

#### 3. Now we are going to apply the one that reference the outer date variable (the clousure one).

```diff
(function () {
   ....

   var print = function (arg) {
       console.log(arg);
   };

   var time = Time();

   print(time.getCurrentTime());
   print(time.getCurrentTime());

+   print(time.getLockedTime());
+   setTimeout(function () {
+       print(time.getLockedTime());
+   }, 1000);
})();

```
