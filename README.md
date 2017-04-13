# angularjs-popups-demo
#### 医护微定制应用产品开发中的高级搜索面板
#### A draft version of [AngularJS-popups-demo](https://github.com/JenifferWuUCLA/medical_AI_micro_customization).

基于 AngularJS 的浮层组件，由 [artDialog](https://github.com/aui/artDialog) 演进而来。angular-popups 是一个严格遵循 AngularJS 架构与 web 标准的组件：

1. 使用 AngularJS 自带的 `ng-if`、`ng-show`、`ng-hide` 控制浮层的显示、销毁
2. 支持 ARIA 规范、无障碍焦点管理、快捷键关闭
3. 完全基于 HTML 标签（指令），无需在控制器中进行配置
4. 可以指定元素或鼠标事件对象（`$event`）对齐
5. 支持模态浮层
6. 对移动端支持友好
6. 轻量（css+js=7kb），不依赖 jQuery 等外部库

## Prerequisites
You'll need [`git`](http://git-scm.com/) and a web browser.


## Getting it
Run the following command to check out a local copy of the code.

```shell
git clone https://github.com/JenifferWuUCLA/medical_AI_micro_customization.git
```

## 使用

支持使用 script 标签或者 webpack、requirejs、seajs 调用：

### script

调用

```html
<script src="lib/angular.js"></script>
<script src="dist/angular-popups.js"></script>
<script>
    var app = angular.module('app', ['angular-popups']);
</script>
```

### webpack

调用
```js
require('angular-popups');
var app = angular.module('app', ['angular-popups']);
```

> angular-popups 依赖 `angular` 这个全局模块

## 指令

包含如下浮层指令：

* [`dialog` 对话框指令](#dialog)
* [`bubble` 气泡指令](#bubble)
* [`notice` 通知消息指令](#notice)
* [`popup` 透明浮层指令](#popup)

### 浮层通用参数

| 名称          | 说明                                     |
| ------------ | ---------------------------------------- |
| ng-if        | 显示或隐藏浮层（DOM 插入或删除）              |
| ng-show      | 显示浮层                                  |
| ng-hide      | 隐藏浮层                                  |
| for          | 指定元素对齐，传入目标元素 ID 即可            |
| align        | 对齐的参数，此参数需要与 `for` 配合使用。默认 `"bottom left"`，可选值：`"top left"` `"top"` `"top right"` `"right top"` `"right"` `"right bottom"` `"bottom right"` `"bottom"` `"bottom left"` `"left bottom"` `"left"` `"left top"` |
| fixed        | 使用固定定位，等同于 CSS `position:fixed`    |
| modal        | 模态浮层                                   |
| duration     | 自动关闭的时间（单位毫秒）                     |
| close        | 浮层关闭事件                                |
| close-action | 配置浮层由什么动作来触发关闭（执行 `close` 事件）。默认 `"esc timeout"` ，所有支持的动作： `"esc timeout outerchick click"` |

> `ng-if`、`ng-show` 如果传入的是 `$event`，则浮层会定位到事件触发位置

## dialog

对话框指令

### 子指令

| 名称               | 说明       |
| ---------------- | -------- |
| dialog-title     | 对话框标题容器  |
| dialog-content   | 对话框内容容器  |
| dialog-buttons   | 对话框按钮容器  |
| dialog-statusbar | 对话框状态栏容器 |

> 对话框子指令中的事件可以使用 `$close()` 这个函数，它会调用通用参数 `close` 中的表达式

## 兼容性

* Chrome
* Firefox
* IE9+

## Running it
Because we are pulling files from a CDN, we are going to need to run medical_AI_micro_customization from a web server. There are a few ways to do this, but one of the easiest ways is to use the npm package `serve`.

The steps are as follows:

1. Install Node.js. You can find all of the information to do that [here](http://nodejs.org/).
2. Install the `serve` package by running `npm install -g serve` from the command line.
3. Navigate to the `angularjs-popups-demo` directory from the command line and run `serve`.
4. Go to [http://localhost:5000](http://localhost:5000) in your browser to see the application.

![Main Page](https://github.com/JenifferWuUCLA/medical_AI_micro_customization/blob/master/image/Medical%20AI%20Search.png)
