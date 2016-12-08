# 代码规范
## CSS规范
### 说明
本CSS规范，参考了`OOCSS`，`SMACSS`，`BEM`理论思路，`Nec`，`BEM`等最佳实践，避开了`BEM`，`Nec`在实战中的不足，结合最新的`Bootstrap`组织框架整理而成。

规范基于`Bootstrap v4`进行了二次开发，实现了一简版DEMO，主要用于研究实践。

DEMO由`Sass`编写而成，内容主要分为两部分：`imports`，`modules`。

1. `imports` 文件夹下主要定义`global variables`，`mixins`，`normalize`等基础配置
2. `modules` 下定义具体模块

具体示例可运行`src/index.html`查看。

**不足与改进**

1. 网易Nec规范，在实践中加入了前缀修饰符如`.u-`，`.m-`，在系统开发中可以很好的辨识出模块所属类别，语义化较好。
不足的是部分节点太过抽象，定义中充斥着大量英文缩写，随着模块数量的增多，复杂的缩写并不利于记忆和使用。
    ```css
    .z-sel   selected缩写
    .z-crt   current缩写
    .s-fc    fontsize缩写
    .f-vam   vertical-align-middle缩写
    ```

2. BEM规范的解决了模块内部定义混乱的问题。在以往的模块定义中，经常会在多个模块使用同一个`class`或者不同名称相同意义的`class`。
    * 使用同一`class`问题在于如果这个`class`在全局中有定义，那么全局属性的改动可能会影响到模块。
    * 在不同模块间使用相似意义的`class`，在语义与规范化方面很差，如`.active`和`.current`经常会在不同模块间距交替使用，然而在上下文中可能表示的是一个意思。
    
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
        /* .current和.active可能表示是同一意思，建议在相同意义下统一class命名如.active */
        .m-list li.current{
            color: red;
            font-weight:bold;
        }

        .m-nav li.active {
            color: blue;
            font-weight:bold; 
        }
      ```
    
    需要注意的是，如果BEM语法使用不当，会导致复杂又冗余的命名方式出现，如： `media-list-container-image`或类似`parentClass-subClass-subClass--modifier`写法。
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

### 参考
* [Nec参考规范](http://nec.netease.com/standard/css-practice.html)
* [CSS规范实战](https://medium.com/@fat/mediums-css-is-actually-pretty-fucking-good-b8e2a6c78b06#.2slca4lo4)
* [Sass参考手册](http://sass.bootcss.com/docs/sass-reference/)
* [OOCSS, SMACSS, BEM基本说明](https://segmentfault.com/a/1190000000704006)