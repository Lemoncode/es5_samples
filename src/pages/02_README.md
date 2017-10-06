## 2. Equality

# Equality it's a bit tricky in javascript. Let's see some results.

* https://developer.mozilla.org/es/docs/Web/JavaScript/Equality_comparisons_and_sameness

### Steps.


#### 1. If we have the same type:

```diff
+var x = 5;
+var y = 7;
+
+console.log(x == y);
```
* The result of this opertion it's false.

#### 2. Both null or undefined

``` diff
+var z; // undefined
+y = null;
+
+console.log(z == y);
```
* The result of this operation it's true.

#### 3. Let's compare string with numbers

* First step

``` diff
+var str = 'string';
+var num = 56;
+
+console.log(str == num);
```

* Second step. Now lets check something that is not a number with undefined.

```diff
+var str1; // undefined
+var num2 = '3d';
+
+console.log(str1 == num2); // false
```

* Third step. Now let's compare null with '0'

```diff
+var str3 = null;
+num3 = '0';
+
+console.log(str3 == num3); // false
```

#### 4. Let's compare boolean with anything

* First we can get with the true value.
```diff
+var boolean = true;
+var object = {};
+
+console.log(boolean == object);
```
* Second we are going to compare to false. Let's ask the students waht is the expected value.

```diff
var boolean = true;
var object = {};

console.log(boolean == object);

+boolean = false;

+console.log(boolean == object);
```
* Ask students what are they expecting.

* Third for last compare undefined with false.

```diff
+var t;

+console.log(false == t);
```

#### 5. Compare object with string

* First compare an object that has a value erqual to a string.

```diff
+var obj = { name:'Jai' };
+var str = 'Jai';
+
+console.log(obj == str);
```
* This one is FALSE.

* Second comapare an array with a string

```diff
+var ar = [1, 2];
+var g = "1,2";
+
+console.log(ar == g);
```
* This one is TRUE.

* Third let's compare 0 with empty string

```diff
+var f = 0;
+var zza = "";
+
+console.log(f == zza);
```

* This one is TRUE.
