# component-doc
现有组件列表，项目依赖：

- [bootstrap](http://www.bootcss.com/)

- [jquery-1.9.1](http://jquery.com/)

## [时间选择插件]()

 插件地址：[bootstrap-datetimepicker](https://eonasdan.github.io/bootstrap-datetimepicker/)

使用方法，在需要初始化的元素上加上`class` `datetimepicker`
```html
<div class='input-group date datetimepicker'>
    <input type='text' class="form-control" />
    <span class="input-group-addon">
        <span class="glyphicon glyphicon-calendar"></span>
    </span>
</div>
```
```js
util.init();
```
### 设置时间区间，后面不能超过见面，前面不能小于后面

在父级元素上加上class datetimepicker_moudle，开始的元素上加上`data-datetimepicker="start"`，结束的元素上加上`data-datetimepicker="end"`

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
```js
util.init();
```


## 验证插件

## datatable插件

## bootstrap-table插件

## 弹窗插件

## 省市区选择插件

## linkTab插件

