## 4. Scope

# The scope of functions on ES5, it's a little bit different from, the scope in other languages. The scope of a variable, in ES5, is defined by the function where is placed. Inner functions, can make reference to outer functions variables.

### Steps.


#### 1. Let's define a function with an internal variable.

```diff
+var greet = function greet () {
+  var hello = 'Hello!!';
+  console.log(hello);
+};
```

* What is going to be the value of hello if we make a reference out of the function? undefined

```diff
var greet = function greet () {
  var hello = 'Hello!!';
  console.log(hello);
};

+console.log(hello);
```

#### 2. Let's make another example.

```diff
+var store = function () {
+  var item = {
+    description: 'Just an item.',
+    value: 45.89
+  };
+
+  function addItem () { // Declaración no invocación.
+    var items = [];
+    items.push(item);
+    return items;
+  }
+
+  return addItem();
+};
```

### 3. Ask what is going to be the result.

```diff
var store = function () {
  var item = {
    description: 'Just an item.',
    value: 45.89
  };

  function addItem () { // Declaración no invocación.
    var items = [];
    items.push(item);
    return items;
  }

  return addItem();
};
+
+console.log(store());
```
