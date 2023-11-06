#### 1.金额格式化

```javascript
function formatMoney(amount) {
  // 将数字转换为字符串，并保留两位小数
  let formattedAmount = amount.toFixed(2);

  // 将字符串按小数点分割为整数部分和小数部分
  let parts = formattedAmount.split('.');
  let integerPart = parts[0];
  let decimalPart = parts[1];

  // 将整数部分每三位加上千分隔符
  let integerWithCommas = integerPart.replace(/\B(?=(\d{3})+(?!\d))/g, ',');

  // 返回格式化后的金额
  return integerWithCommas + '.' + decimalPart;
}
```
```

```

#### 2.判断字符串是否为空

```javascript
//判断字符串是否为空
isEmpty: function(str) {
	if (str === '' || str === undefined || str === null) {
		return true;
	} else {
		return false;
	}
}
```
#### 3.判断变量的类型

```javascript
const trueTypeOf = (obj) => Object.prototype.toString.call(obj).slice(8, -1).toLowerCase();
```
```javascript
trueTypeOf('');     // string
trueTypeOf(0);      // number
trueTypeOf();       // undefined
trueTypeOf(null);   // null
trueTypeOf({});     // object
trueTypeOf([]);     // array
trueTypeOf(0);      // number
trueTypeOf(() => {});  // function
```

#### 4.检测对象是否为空

```
const isEmpty = obj => Reflect.ownKeys(obj).length === 0 && obj.constructor === Object;
```

```
```

#### 5.交换两个变量的值

这行代码的语义是交换两个变量的值，而不需要使用额外的临时变量。

```
[foo, bar] = [bar, foo];
```

#### 4.判断数组是否为空

该方法用于判断一个数组是否为空数组，它将返回一个布尔值：

```javascript
const isNotEmpty = arr => Array.isArray(arr) && arr.length > 0;

isNotEmpty([1, 2, 3]);  // true
```



















































































































