#函数

@(课程关键字)[函数 | 函数形参|函数arguments|函数return|匿名函数]
**函数：**中文意思是方法和功能。
**函数**就是包裹在花括号中的代码块，前面使用了关键词 function + 函数名
```
function methods() {
	// 这里是要执行的代码
	var num = 1 + 2;
}
```
**函数** 分为**定义**和**执行**两个阶段上面的代码只是**函数的定义**。
函数的执行语法是什么样呢？  **函数名**+**()**看以下代码？
```
	methods();// 这就是函数的执行，函数名()
```
##参数
>我们在函数定义的时候，会根据函数方法内部的需要，定义出一个或多个变量，及**形参变量**，
>方便函数内部调用。
>调用带**参数**的**函数**
>在**调用函数**时，您可以向其**传递值**，这些值被称为**参数(实参)**，这些实参就是给形参赋值，可以在函数中使用。
>您可以定义任意多的形参，和传递任意多的实参，由逗号 (,) 分隔。传递的实参和形参，顺序是一一对应的。
```
				   //形参变量
function welcomeFn(name,job) {
	alert("Welcome " + name + ", the " + job);
}
welcomeFn('赵煊','教学'; // 实参
```
##return 
>有时，我们会希望函数内部处理的值，在函数外部调用它，那么我们就要把这个值返给需要调用的地方。怎么实现呢？
通过使用 return 语句就可以实现。
在使用 return 语句时，函数会停止执行，return后边的语句不会在执行，并返回指定的值。
语法
function myFunction() {
		var x=5; // 在函数内部我们定义了一个 x 值为 5
		return x; // 我们在函数外需要他，就该返回给外边
}

var need = myFunction(); need 变量的值为5,就是函数myFunction 执行后返回的值 及x,值为5。

>计算两个数字的乘积，并返回结果：
function myFunction(a,b) {
		return a*b;
}
document.getElementById("demo").innerHTML=myFunction(4,3);
##arguments 
>在所有的函数中，都可以使用特殊对象 arguments。arguments是一个类数组，具有数组的所有特性，可以通过索引直接访问其中每一项。
arguments.length = 函数**执行**时传递的**实参**数量总和。
```
function sayHi(param1, param2) {
  if (arguments[0] == "bye") {
    return;
}
  alert(arguments[0]);
}
sayHi('bye');
```
>arguments 存在一个callee属性，callee的值是当前执行函数本身。
```
// 任意数求和
	function sum(){
        var thatResult = 0;
        for (var i=0; i<arguments.length; i++) {
            thatResult += arguments[i];
        }
        return thatResult;
    }

     console.log(sum(2, 3));
	 console.log(sum(2, 3, 4, 5, 6));
```
##匿名函数
>匿名函数分为两种，函数表达式和自执行函数。
>匿名函数就是相对于我们定义的函数方法，就是少了名字，举一下例子啊
```
	// 函数表达式
	var thatSum = function (){
        var thatResult = 0;
        for (var i=0; i<arguments.length; i++) {
            thatResult += arguments[i];
        }
        return thatResult;
    }
    thatSum();// 函数表达式的执行
    
    //自执行函数，自执行的函数写法有好多种
	(function (){
	     var thatResult = 0;
         for (var i=0; i<arguments.length; i++) {
            thatResult += arguments[i];
         }
        return thatResult;
	})();

	~function (num1, num2) {
        console.log(num1 + num2);
        console.log(arguments)
    }(1, 2, 3);

    !function (shui, dou) {
        var doujiang = shui + dou;
        console.log(doujiang+'的豆浆');
    }('农夫山泉', '红豆');

```