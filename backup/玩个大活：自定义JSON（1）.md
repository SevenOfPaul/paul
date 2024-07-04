今天我们来玩个大活：用cpp写一个**自定义JSON解析器**，第一天我们先来简单介绍下JSON，
## JSON类型介绍
类型 | 描述
-- | --
数字型（Number） | JavaScript 中的双精度浮点型格式
字符串型（String） | 双引号包裹的 Unicode 字符和反斜杠转义字符
布尔型（Boolean） | true 或 false
数组（Array） | 有序的值序列
值（Value） | 可以是字符串，数字，true 或 false，null 等等
对象（Object） | 无序的键:值对集合
空格（Whitespace） | 可用于任意符号对之间
null | 空

使用JSON最简单的方式就是打开浏览器使用浏览器自带的js
```typescript
const str=JSON.stringify({name:"张三"});
const obj=JSON.parse(str);
console.log(str,obj);
```
![1720103016669](https://github.com/SevenOfPaul/paul.github.io/assets/83870824/a031e40d-f4b3-48da-86c6-1a56d5e310dd)
## 设置接口
我们可以使用`enum class`语法来定义MyJson的类型
```cpp
enum class JsonType {
    Null,Number,Boolean,String,Array,Object
};
```
欲知后事如何，且听下回分解。
