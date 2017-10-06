## 8. Playing with arrays

### Steps.

#### 1. Let's start by defining a variable that will be our array, and a function to add items to it.

```diff
+var students = [];
+
+var addStudent = function (student) {
+  students.add(student);
+};
```

#### 2. Let's now define our student. To define our student we are going to use the reveal pattern.

```diff
var students = [];

var addStudent = function (student) {
  students.add(student);
};

+var Student = function (id, name) {
+  return {
+    id: id,
+    name: name,
+    showName: function () {
+      return this.name;
+    },
+    showId: function () {
+      return this.id;
+    }
+  };
+};
```

#### 3. Array in javascript language provides a method to get the items in the collection ordered. Let's define a couple of callbacks that will describe how the items will be sort.

```diff
var students = [];

var addStudent = function (student) {
  students.add(student);
};

+var orderById = function (first, second) {
+  return first.id - second.id;
+};

+var orderByName = function (first, second) {
+  return first.name.localeCompare(second.name);
+};

var Student = function (id, name) {
  return {
    id: id,
    name: name,
    showName: function () {
      return this.name;
    },
    showId: function () {
      return this.id;
    }
  };
};
```
#### 4. Just to make easy to use on 'script client' the use of these two callbacks let's define another function.

```diff
var students = [];

var addStudent = function (student) {
  students.add(student);
};

+var sortStudents = function(key) {
+  if (key === 'id') {
+    return students.sort(orderById);
+  }
+
+  if(key === 'name') {
+    return students.sort(orderByName);
+  }
+};

var orderById = function (first, second) {
  return first.id - second.id;
};

var orderByName = function (first, second) {
  return first.name.localeCompare(second.name);
};

var Student = function (id, name) {
  return {
    id: id,
    name: name,
    showName: function () {
      return this.name;
    },
    showId: function () {
      return this.id;
    }
  };
};
```
#### 5. Now with this on place, let's declare a couple of students.

```diff
....
+var std1 = Student(1, 'Lau');
+var std2 = new Student(3, 'Ana');
```
* Ask what is the different between this two methods.
* If we use debugger, we can see that both variables has the same shape.

###NOTE: A literal object will have the same prototype. 

```diff
+var date = Date(); // Points to Object the base.
+var date2 = new Date(); // Points to Object the base.
```
* Now if we do the same with Date, the result is quite different.
* new keyword is an operator on javascript that basically what is doing get this initialize(make that points to the instance of the object) and make that the pointer __proto__ points to prototype.

```diff
+console.log(date.__proto__); // Points to String
+console.log(date2.__proto__); // Points to Date
```
#### 6. Let's push some elements inside our array.

```diff
...
-var std1 = Student(1, 'Lau');
-var std2 = new Student(3, 'Ana');
-
-var date = Date();
-var date2 = new Date();
-
-console.log(std3.__proto__);

+var std1 = Student(1, 'Lau');
+students.push(std1);
+var std2 = Student(3, 'Jai');
+students.push(std2);
+var std3 = Student(5, 'Fer');
+students.push(std3);
+var std4 = Student(99, 'Zan');
+students.push(std4);
+var std5 = Student(2, 'Berts');
+students.push(std5);
```

#### 7. Now with this on place let's call our sortStudents method.

```diff
....
+var sortedById = sortStudents('id');
+console.log(sortedById);
+var sortedByName = sortStudents('name');
+console.log(sortedByName);
```
* Discuss results with students.
* Open first the SECOND result on console.
