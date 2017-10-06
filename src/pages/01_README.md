## 1. Objects

# Objects in javascript are declare with literal notation. Let's see how we can create them.

### Steps.


#### 1. First we create a plain object with a couple of properties.

```diff
+var student = {
+  name: 'Lau',
+  lastName: 'Salas'
+};
```

#### 2. We can create 'properties' inside objects more complex such as arrays or even other objects.

```diff
var student = {
+  subjects: [
+    'dance',
+    'puppet',
+    'play'
+  ],
  name: 'Lau',
  lastName: 'Salas'
};
```

#### 3. We can also add methods.

```diff
var student = {
  subjects: [
    'dance',
    'puppet',
    'play'
  ],
+  doHomework: function(homeWork) {
+    console.log("I've done my duties!!");
+  },
  name: 'Lau',
  lastName: 'Salas'
};
```

#### 4. Something ineresting about objects is that we can see them on javascript as bag of other properties. Even we can iterate over its properties.

```diff
var student = {
  subjects: [
    'dance',
    'puppet',
    'play'
  ],
  doHomework: function(homeWork) {
    console.log("I've done my duties!!");
  },
  name: 'Lau',
  lastName: 'Salas'
};

+var showMyValues = function (obj) {
+  for (var key in obj) {
+    var value = obj[key];
+    console.log(value);
+
+    if (Array.isArray(value)) {
+      for (var i = 0; i < value.length; i++) {
+        console.log(value[i]);
+      }
+    }
+  }
+};

+showMyValues(student);
```

