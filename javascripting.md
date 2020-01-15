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

