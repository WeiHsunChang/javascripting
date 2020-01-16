# javscripting

# 介紹
```js
console.log('hello');
```

# 變數(variables)
變數：一個可以引用具體值得名字
變數透過使用 var 及緊隨其後的變數名來宣告

```js
例：
var example;

也可在宣告同時賦予值
var example = 'some string';
```

# 字串(string)
字串：被引號包裹起來的任意的值
單引號或雙引號效果是一樣的
```js
'this is a string'
"this is also a string"
```

### 字串長度
可以使用 .length 來得到一個字串的長度
```js
var example = 'example string';
console.lgo(exmple.length); => 14
```

### 修改字串
可以使用 .replace() 取代字串中的內容
```js
var example = 'this example exists';
example = example.replace('exists','is awesome');
console.log(example);
```


# 數字
integer is like 2、14、4356、-32  
float is like 3.14、1.5、100.78932

```js
宣告方法：
var integer = 123;
var float = 3.14;
```

### 數字取整數
除了基本的數學運算，比如 ＋，－，＊，/，和％  
複雜的數學運算可使用 Math Object

```js
var roundUp = 1.5;
var rounded = Math.round(roundUp);
console.log(rounded); => 2
```

### 數字轉字串
可以使用 .toString() 方法。

```js
var n = 128;
n = n.toString();
console.log(n); => 128(string)
```


# IF條件式
條件語句基於一個特定的布林（Boolean）值來改變程序的流程。 
```js
if (boolean) {  
    //boolean為true時，則執行此處程式  
}
else {  
    //boolean為false時，執行此處程式
} 
```

例如
```js
var fruit = 'orange';
var str_len = fruit.length;
if(str_len>5){
    console.log('The fruit name has more than five characters.');
}
else{
    console.log('The fruit name has five characters or less.');
}
```

# For 迴圈

```js
for (var i = 0; i < 10; i++) {  
    // log the numbers 0 through 9  
    console.log(i)  
}

透過 條件式 i < 10; 控制迴圈次數，條件式為true時迴圈才繼續被執行
i++ 代表每次回圈結束後 i 的值加一
```

# 陣列(Array)
陣列：由一組值構成的列表
```js
var pet = ['cat', 'dog', 'rabbit'];
```

### 陣列過濾
使用 .filter() 方法可以達到過濾陣列的目的
```js
var numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
var filtered = numbers.filter(function evenNumbers(number){
    return number % 2 == 0;
})
console.log(filtered); => [2, 4, 6, 8, 10]
```

### 存取陣列中的值

陣列中的元素可以透過索引值(index)來訪問  
index 就是一個 integer ，從0開始到陣列長度減一

```js
var numbers = [1, 2, 3];
console.log(numbers[0]) => 1
```

### 以回圈存取陣列中的值

```js
var pets = ['cat', 'dog','rat'];
for(var i=0; i<pets.length; i++){
    pets[i] = pets[i] + 's';
}
console.log(pets); => ['cats', 'dogs', 'rats']
```


# 物件(Object)
物件像陣列一樣，也是一組值的集合，但不同的是，  
物件裡的值(Value)被鍵（Key）所標識，而非整數。
```js
key : Value

var pizza = {
    toppings : ['cheese', 'sauce', 'pepperoni'], => Value 為 array
    crust : 'deep dish', => Value 為 string
    serves : 2 => Value 為 integer
};
```

### 物件的屬性
屬性：物件所包含的key和value的pair  
操作屬性的方式與操作陣列類似
```js
var food = {
    types : 'only pizza'
};
console.log(food.types); => only pizza
console.log(food['types']) => only pizza
使用中括號和點都可以獲得相同結果
```


# 函式(Function)
函式：一段程式碼，程式碼對輸入做處理，然後產生輸出

```js
function example(x){
    return x * 2;
}
可以像下面這樣呼叫函式，得到數字 10;
example(5)

```

### 函式的參數(Arguments)

一個函式可以宣告為接受任意數量的參數。  
參數可以是任意的型別，例如字串、數字、物件，甚至是另一個函式

```js
function math(num1, num2, num3){
    return num2 * num3 + num1;
}
呼叫函式時，需給相對應數量的參數
console.log(math(53,61,67)); => 61 * 67 + 53 = 4140
```


# 作用域
```js
var a = 4;    // a 是一個全域變數，它可以被下面的函式存取  
function foo() {  
    var b = a * 3;    
    // b 不能夠在 foo 函式以外被存取，但是可以被定義於 foo 內部的其他函式存取  
       
    function bar(c) {  
        var b = 2;  // 另一個新的 `b` 變數被建立在 bar 函式的作用域內  
                    // 對這個新的 `b` 變數的改變並不會影響到舊的 `b` 變數  
        console.log( a, b, c );  
    }  
       
    bar(b * 4);  
} 
foo(); // 4, 2, 48  
```   
### 立即函式（IIFE, Immediately Invoked Function Expression）  
IIFE : 用來建立區域作用域的常用方法。  
```js
(function(){ // 這個函式語法被一組小括號括起來  
    // 在這裡定義的變數  
    // 不能夠在這個函式外被存取  
})(); // 這個函式立即被執行 

例如：
var a = 1, b = 2, c = 3;  
(function firstFunction(){  
    var b = 5, c = 6;  
    (function secondFunction(){  
        var b = 8;  
        console.log("a: "+a+", b: "+b+", c: "+c); => a: 1, b: 8, c: 6
        (function thirdFunction(){  
            var a = 7, c = 9;  
            (function fourthFunction(){  
                var a = 1, c = 8;
            })();  
        })();  
    })();  
})();

```