# 云数科技 JavaScript 代码规范
## 代码架构
目前我们的前端项目均采用 Node.js / Express / Pug 开发，因此代码结构规范如下：
```
├── node_modules
├── static
│   ├── lib
│   ├── css
│   ├── img
│   ├── js
│   └── favicon.ico
├── views
├── CHANGELOG.md
├── app.js
└── Makefile
```
其中：
- `node_modules`：存放 Node.js 的组件库，不得放入 git repo 中；
- `static/lib`：存放 JavaScript 组件库，每个组件根目录需要命名为 `<name>-<version>` 格式，例如：`jquery-1.10`；
- `static/css`、`static/js`：分别对应 `views/*.pug` 的 CSS 和 JavaScript 组件，例如：`views/index.pug`、`css/index.css` 及 `js/index.js`，每个 pug 至多拥有一个对应 CSS 及 JavaScript 组件； 
- `static/img`：存放静态图片；
- `static/favicon.ico`：网站图标；
- `views`：存放 pug 文件；
- `CHANGELOG.md`：存放更新，详见版本历史文件规范；
- `app.js`：Node.js 启动文件，详见启动文件规范；
- `Makefile`：Make 启动文件，详见启动文件规范。

##  变量命名
对于不同的变量类型，命名规则会有不同：
变量类型 | 命名规则 | 示范
--- | --- | ---
全局变量 | 全部大写 | `var GLOBAL_VAR = '';`
普通变量 | 小写下划线 | `var local_variable = '';`
重载函数 | Camel Case | `String.prototype.djangoFields = function(){};`
普通函数 | 小写下划线 | `function show_dialog(){}`
文件 / URL 路径 | 小写中划线 | `index-2.pug`
JavaScript 类 | Pascal Case | `var NewDashboard = function (){};`
CSS 类 | 小写中划线 | `md-12`

## 注释
请参照如下范例：
```
// 处理时间
var start_timer = moment().startOf('month').format('YYYY-MM-DD');
// Process end timer
var end_timer = moment().format('YYYY-MM-DD');
// TODO: Modify end timer 处理 timer 时间
end_timer = '\u03bcs'; // 'μs'
```
如上范例，注释需要注意以下几点：
- 注释正文与 `//` 之间需要有一个空格；
- 注释正文需要采用 sentence case，中文与英文之间需要有空格；
- TODO 需要使用英文冒号，冒号后的正文采用 sentence case；
- 段落性的注释，如标注下一段代码的功能，必须换行，不得放置于代码后端；
- 特殊情况（目前仅非 ASCII 字符处理）时，可以注释于代码后端，且代码正文与 `//` 之间需要有一个空格。

## 启动文件
### Node.js 启动文件
Nobody here but us chickens.
### Make 启动文件 
Nobody here but us chickens.

## 其他
- 非 ASCII 且非主要语言字符请使用转义及注释，不要仅注释或直接写入字符串中，如：
```
const units = '\u03bcs'; // 'μs'
```

**Copyright 2015 - 2017 云数信息科技（深圳）有限公司**
