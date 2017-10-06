## 5. Precedence

# Now let's talk about variables prcedence. What will happen if  I got a global variable, and the same named variable declare inside a function, Which value will be applied.

### Steps.


#### 1. Let's define the variable in the global scope and the same variable inside the function.

```diff
+var g = "I'm on global";

+var func = function () {
+  var local = "I'm in local";
+  var g = "I'm in local as well'";
+  console.log(local);
+  console.log(g);
+};
```

### 2. Ask what are the expected values

```diff
var g = "I'm on global";

var func = function () {
  var local = "I'm in local";
  var g = "I'm in local as well'";
  console.log(local);
  console.log(g);
};

+console.log(g);
+func();
```

* Conclusion the inner declare variables, even with the same name as the global ones have preference.
