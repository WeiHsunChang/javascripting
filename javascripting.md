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