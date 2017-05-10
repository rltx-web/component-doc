# component-doc
现有组件列表，项目依赖：

- [bootstrap](http://www.bootcss.com/)

- [jquery-1.9.1](http://jquery.com/)

- util

## 时间选择插件

 插件地址：[bootstrap-datetimepicker](https://eonasdan.github.io/bootstrap-datetimepicker/)

使用方法，在需要初始化的元素上加上`class` `'datetimepicker'`：

html部分代码：
```html
<div class='input-group date datetimepicker'>
    <input type='text' class="form-control" />
    <span class="input-group-addon">
        <span class="glyphicon glyphicon-calendar"></span>
    </span>
</div>
```
js部分代码：
```js
util.init();
```
util内对应代码：
```js
var util = (function () {
    init: function () {
        var _this = this;
        if ($('.datetimepicker').length) {
            _this.dateTimePicker();
        }
    },
    dateTimePicker: function () { // dateTimePicker
        // dateTimePicker code
    }
});
```
### 设置时间区间，后面不能超过见面，前面不能小于后面

在父级元素上加上class datetimepicker_moudle，开始的元素上加上`data-datetimepicker="start"`，结束的元素上加上`data-datetimepicker="end"`：

html部分代码：
```html
<div class="container datetimepicker_moudle">
    <div class='col-md-5'>
        <div class="form-group">
            <div class='input-group date datetimepicker' data-datetimepicker="start">
                <input type='text' class="form-control date-value" />
                <span class="input-group-addon">
                    <span class="glyphicon glyphicon-calendar"></span>
                </span>
            </div>
        </div>
    </div>
    <div class='col-md-5'>
        <div class="form-group">
            <div class='input-group date datetimepicker' data-datetimepicker="end">
                <input type='text' class="form-control" />
                <span class="input-group-addon">
                    <span class="glyphicon glyphicon-calendar"></span>
                </span>
            </div>
        </div>
    </div>
</div>

```
js部分代码：
```js
util.init();
```

## 验证插件

插件地址：[jqueryvalidation](http://jqueryvalidation.org/),使用方法：

首先我们会有一个`form`表单,`submit`button必须在`form`表单内部，需要验证的元素上面需要`name`，因为我们是根据`name`值来选择元素验证的。

html部分代码：
```html
<form class="cmxform" id="commentForm" method="get" action="">
    <fieldset>
        <div class="form-group">
            <label for="usernamea">number (required, at least 2 characters)</label>
            <input id="usernamea" name="number" class="form-control" type="text">
        </div>
        <div class="form-group">
            <label for="usernamea">number (required, at least 2 characters)</label>
            <input id="usernamea" name="number" class="form-control" type="text">
        </div>
        <div class="form-group">
            <label for="username">Name (required, at least 2 characters)</label>
            <input id="username" name="username" class="form-control" type="text">
        </div>
        <div class="form-group">
            <label for="cemail">E-Mail (required)</label>
            <input id="cemail" type="email" class="form-control" name="email" required>
        </div>

        <div class="form-group">
            <label for="ccomment">Your comment (required)</label>
            <textarea id="ccomment" name="comment" class="form-control" required></textarea>

            <label for="hide">hide</label>
            <input id="hide" class="form-control" name="hide" style="opacity: 0;">
        </div>
        <p>
            <input class="submit" type="submit" value="Submit">
            <input id="submit" type="button" value="add">
        </p>
    </fieldset>
</form>
```
js部分代码：

验证通过后我们可以自己选择成功后的执行函数：
- submitType=auto,执行validateDone()
- submitType=submit, 直接提交表单
- submitType=post, 用post方法提交表单
```js
 $(function () {
    var validatorOption = {
        ele: ".cmxform",
        submitType: "auto",//提交的方法post或者submit或者auto
        postUrl: "111",//post地址，submitType为post的时候才需要填写
        rules: {
            number: {
                required: true,
                minlength: 3
            },
            username:{
                required: true,
                minlength: 3
            },
            hide:{
                required: function(ele){
                    //console.log(ele)
                }
            },
            date:{
                required: true,
                mobileNL: true
            }
        },
        messages:{
            username:{
                required: "亲，用户名不能为空",
                minlength: jQuery.validator.format("亲，用户名不能小于{0}个字符")
            },
            domain:{
                //domain: "aaa"
            },
            email:{
                remote:"邮箱已存在"
            }
        },
        postDone: function(data){//post 成功后的函数
            console.log(data);
        },
        validateDone: function(form){//type为auto的时候的成功后执行的函数
            console.log(form);
            $.ajax({
                url: form.action,
                type: form.method,
                data: $(form).serialize(),
                success: function(response) {
                    $('#answers').html(response);
                }
            });
        }
    };
    util.initValidatorFrom(validatorOption);
});
```
util内代码：
```js
var util = (function () {
    initValidatorFrom: function (option) { // 初始化配置
    },
    onValidatorFormSubmit: function (form) { // 提交from

    },
    onValidatorFormPost: function (option) {// post提交from
    },
    popover: function (ele, mes ,state) {

    },
    tooltip: function (ele, mes ,state) {
    }
});
```

## datatable插件

## bootstrap-table插件

## 弹窗插件

## 省市区选择插件

## linkTab插件

## select2

## webupload

