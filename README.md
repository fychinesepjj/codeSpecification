# Code Specification
# CSS代码规范
## 说明
本CSS规范，参考了`OOCSS`，`SMACSS`，`BEM`理论思路，`Nec`，`BEM`等最佳实践，避开了`BEM`，`Nec`在实现中的不足，结合了最新`Bootstrap`框架组织而成。

在规范基础上，实现一DEMO，基于`Bootstrap v4`开发，主要用于实践研究。

DEMO由`Sass`编写而成，内容主要分为两部分：`imports`，`modules`。

1. `imports` 文件夹下主要定义`global variables`，`mixins`，`normalize`等基础配置
2. `modules` 下定义具体模块

具体示例可运行`src/index.html`查看。

**不足与改进**

1. 网易Nec规范，在实践中加入了前缀修饰符如`.u-`，`.m-`，在系统开发中可以很好的辨识出模块所属类别，语义化较好。
不足的是部分节点太过抽象，定义中充斥着大量英文缩写，随着模块数量的增多，复杂的缩写并不利于记忆和使用。
    ```css
    .z-sel {}   /* selected 缩写 */
    .z-crt {}   /* current 缩写  */
    .s-fc  {}   /* fontsize 缩写 */
    .f-vam {}   /* vertical-align-middle 缩写 */
    ```

2. BEM规范的解决了模块内部定义混乱的问题。在以往的模块定义中，经常在多个模块使用同一`class`或不同名称意义相似的`class`。
    * 使用同一`class`问题在于如果这个`class`在全局中有定义，那么全局属性的改动可能会影响到模块。
    * 在不同模块间使用相似意义的`class`，在语义与规范化方面较差，如`.active`和`.current`可能会在不同模块间距交替使用，然而在上下文中表示的是一个意思。
    
      *Example-1*
      ```css
        /* .title全局定义可能会影响到模块中.title定义 */
        .title {padding: 10px 0;}
        .m-nav .title{
            color: red;
            height: 120px;
        }
        .m-footer .title {
            color: blue; 
        }
      ```
      *Example-2*
      ```css
        /* .current和.active可能表示的是同一意思，建议在相同情况下统一命名，如.active */
        .m-list li.current{
            color: red;
            font-weight:bold;
        }

        .m-nav li.active {
            color: blue;
            font-weight:bold; 
        }
      ```
    
    需要注意的是，如果BEM语法使用不当，会导致复杂又冗余的命名方式出现，如： `media-list-container-image`或类似`parentClass-subClass-subClass--modifier`定义。
    ```html
      <!--冗余写法-->
      <div class="media-list">
          <div class="media-list-container media-list-container--highlight">
              <img class="media-list-container-image" src="rean.jpg" alt="">
          </div>
          <div class="media-list-body">
              <p class="media-list-body-text">本作的主角，帝国北部地方贵族施瓦泽男爵的养子，也是托尔兹士官学校特科班“Ⅶ组”的成员。</p>
          </div>
      </div>

      <!--简单写法-->
      <div class="media-list">
          <div class="media-list-container">
              <img class="media-list-image" src="rean.jpg" alt="">
          </div>
          <div class="media-list-body">
              <p class="media-list-text">本作的主角，帝国北部地方贵族施瓦泽男爵的养子，也是托尔兹士官学校特科班“Ⅶ组”的成员。</p>
          </div>
      </div>

      <!--更简单写法:运用驼峰写法，当然这种混合使用的手法是仁者见仁智者见智的事情-->
      <div class="mediaList">
          <div class="mediaList-container">
              <img class="mediaList-image" src="rean.jpg" alt="">
          </div>
          <div class="mediaList-body">
              <p class="mediaList-text">本作的主角，帝国北部地方贵族施瓦泽男爵的养子，也是托尔兹士官学校特科班“Ⅶ组”的成员。</p>
          </div>
      </div>
    ```
    BEM常用几种用法解读：
    ```css
    .media-body--bordered  {}                 /* 常用写法    建议*/
    .mediaList-innerImage--bordered  {}       /* 驼峰写法    建议*/
    .media-list-inner-image--bordered  {}     /* 连字符写法  不建议*/
    .media_list-inner_image--bordered  {}     /* 连字符+下划线写法  不建议*/
    ```
    一般不建议连字符`-`与下划线`_`一起使用，视觉上容易混淆，在单词过长的情况下建议使用驼峰写法缩短长度，如`.mediaList-innerImage--bordered`。

## 规范说明
**前缀符**
1. `g-` 布局
2. `ui-`组件
3. `m-` 模块
4. `u-` 元件
5. `f-` 功能
6. `z-` 状态
7. `s-` 皮肤
8. `js-` js相关

```css
.g-container {}
.m-nav {}
.u-btn {}
.f-float-left {}
.z-open {}
.s-bg-red {}
.js-send {}
```
* 前缀后，*单个单词*命名可以是简写，也可以是完整单词，如果单词有缩写形式建议使用缩写，如`.u-button`缩写成`.u-btn`，`.m-navigation`缩写成`.m-nav`。
* 前缀后，*多个单词*拼写情况，除了常用定义使用缩写:

    ```css
    lg === large
    sm === small
    md === medium
    xl === xlarge
    fl === float-left
    fr === float-right
    mx === margin-x方向
    my === margin-y方向
    ml === margin-left
    mr === margin-right
    mt === margin-top
    mb === margin-bottom
    px === padding-x方向
    py === padding-y方向
    pl === padding-left
    pr === padding-right
    pt === padding-top
    pb === padding-bottom
    ```
     其他都统一使用连字符`-`串联，如

    ```css
    .f-float-none
    .f-rounded-top
    .f-rounded-right
    .f-text-left
    .f-align-top
    .f-text-upper
    .f-font-bold
    .f-overflow-hidden
    .f-inline-block
    ...
    ```

**模块定义**

* 对于模块以及模块内元素定义，单个单词情况下使用普通连字符，多个单词情况下使用驼峰写法:
    ```html
    <!--单个单词情况-->
    <div class="m-media">
        <div class="media-container"></div>
    </div>

    <!--多个单词情况-->
    <div class="m-mediaList">
        <div class="mediaList-imageContainer"></div>
    </div>
    ```

* 模块内不元素不再添加前缀符`.m-`：
    ```html
    <div class="m-mediaList">
        <!--错误写法-->
        <div class="m-mediaList-imageContainer"></div>
        <!--正确写法-->
        <div class="mediaList-imageContainer"></div>
    </div>
    ```

* 模块内可以嵌套其他模块:
    ```html
    <div class="m-media">
        <div class="media-container"></div>
        <!--分页模块-->
        <ul class="m-pagination">
            <li class="pagination-item"><a class="pagination-link"  href="#">&laquo;</a></li>
            <li class="pagination-item"><a class="pagination-link" href="#">1</a></li>
        </ul>
    </div>
    ```

**元素定义**
* `.u-`：主要用于单个元素类型，`.u-button`，`.u-h1`，`.u-blockquote`
* `.m-`：主要用于复合型元素类型，`.m-pagination`，`.m-breadcrumb`
* 对于扩展元素如`pagination-lg`，`btn-lg`需要统一加上前缀符:`.m-pagination-lg`，`.u-btn-lg`
* 如果对`.m-`模块内元素进行重定义，一般可以采用两种形式：
   1. `<table class="m-table m-table-inverse"><thead></thead></table>` 外层包裹`m-table-inverse`进行重定义，此时需要有`.m-`前缀，主要用于同时对多个元素重定义。
        ```css
        .m-table-inverse {
            color: $body-bg;
            background-color: $table-bg-inverse;
            th,
            td,
            thead th {
                border-color: $body-bg;
            }
        }
        ```
    2. `<table class="m-table"><thead class="table-head-inverse"></thead></table>`，`table-head-inverse`不需要`.m-`前缀符，主要用于单个元素重定义。

## DEMO结构
```
* demo  // boostrap v4删减整合版
* test  // sass编译，语法调试
* src
  * sass
    * imports
        _custom_variables.scss  // 覆写_variables.scss配置，主要用于自定义
        _variables.scss         // 存放全局变量，颜色，字体，大小等
        _mixins.scss            // sass工具类，主要用于复用css代码
        _normalize.scss         // 第三方normlize定义，重置浏览器css样式
        _reboot.scss            // 在normalize基础上，二次重置浏览器css样式
        _type.scss              // 主要是h1, pre, code等样式定义
        _utilities.scss         // 工具类，定义了浮动，边距，高度等常用样式类型
    * modules
        _breadcrumb.scss        // 面包屑导航
        _buttons.scss           // 通用按钮
        _forms.scss             // 表单相关元素
        _grid.scss              // 网格布局
        _input_group.scss       // 组合输入栏
        _pagination.scss        // 分页
        _tables.scss            // table组件
  * media
    * css // sass编译后文件存放目录
```
### 参考
* [Nec参考规范](http://nec.netease.com/standard/css-practice.html)
* [CSS规范实战](https://medium.com/@fat/mediums-css-is-actually-pretty-fucking-good-b8e2a6c78b06#.2slca4lo4)
* [Sass参考手册](http://sass.bootcss.com/docs/sass-reference/)
* [OOCSS, SMACSS, BEM基本说明](https://segmentfault.com/a/1190000000704006)