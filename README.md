# KnockoutJS 官方演示视频代码

照着视频敲了一遍，可能略有不同，但能说明问题。

- 视频地址 https://channel9.msdn.com/Events/MIX/MIX11/FRM08
- 官方网站 http://knockoutjs.com/index.html

## Knockout

html
```html
<input data-bind="value:firstName">
FirstName:<span data-bind="text:firstName"></span>
```
```js
var viewModel = {
    firstName: ko.observable(''), //双向绑定，可观察属性，注意：这将转变为一个方法
}
ko.applyBindings(viewModel); //绑定 viewModel 很重要，没这部都不起作用
```


## Knockout-Validation
```js
ko.validation.localize({
    required: '必填字段',
    min: '输入值必须大于等于 {0}',
    max: '输入值必须小于等于 {0}',
    minLength: '至少输入 {0} 个字符',
    maxLength: '输入的字符数不能超过 {0} 个',
    pattern: '请检查此值',
    step: '每次步进值是 {0}',
    email: 'email地址格式不正确',
    date: '日期格式不正确',
    dateISO: '日期格式不正确',
    number: '请输入一个数字',
    digit: '请输入一个数字',
    phoneUS: '请输入一个合法的手机号(US)',
    equal: '输入值不一样',
    notEqual: '请选择另一个值',
    unique: '此值应该是唯一的'
});

// 示例 
var viewModel = {
            name: ko.observable('windy').extend({ max: 3, message:'最多3个字符' }),
            tel:ko.observable('').extend({ pattern: { params: /^(?:04\d{2}|\({1}04\d{2}\){1})\s{0,1}(\d{3}(\s{0,1})\d{3})$/, message: "这不是一个电话号码."} });
            add:ko.observable('')
 }


```