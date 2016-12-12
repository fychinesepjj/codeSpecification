# CSS规范 - 示例用法
具体示例可运行`src/index.html`查看
## 工具类
* 功能
```css
.f-mx-auto        /* margin X方向 auto */
.f-m-0
.f-mt-0
.f-mr-0
.f-mb-0
.f-ml-0
.f-mx-0           
.f-my-0          /* margin Y方向 0 */
...  [0-12]
.f-p-0
.f-pt-0
.f-pr-0
.f-pb-0
.f-pl-0
.f-px-0          /* padding X方向 0 */
.f-py-0          /* padding Y方向 0 */
... [0-12]

.f-border-none
.f-border-top-none
.f-border-bottom-none
.f-border-left-none

.f-rounded-circle
.f-rounded-none

.f-full-width    /* width:100% */
.f-full-height   /* height:100% */

/* vertical-align */
.f-align-baseline
.f-align-top
.f-align-bottom
.f-align-middle
.f-align-text-bottom
.f-align-text-top

/* text-align and text */
.f-text-justify
.f-text-nowrap
.f-text-truncate
.f-text-left
.f-text-right
.f-text-middle
.f-text-lower
.f-text-upper
.f-text-cap
.f-text-white
.f-text-hide

.f-font-normal
.f-font-bold
.f-font-italic

.f-hidden-print
.f-overflow-hidden
.f-overflow-scroll

.f-inline
.f-inline-block
.f-block

.f-relative
.f-absolute
.f-fixed
.f-zoom

.f-fl
.f-fr
.f-float-none
.f-clearfix

.f-underline
.f-decoration-none
.f-decoration-overline
.f-cursor
.f-cursor-pointer
.f-user-select-none
```

* 状态
```css
.z-selected
.z-current
.z-active
.z-show
.z-hidden
.z-invisible
.z-error
.z-disabled
.z-open
.z-close
```

* 皮肤样式
```css
.s-font-red
.s-bg-red
.s-border-red
```

## 布局类
```css
.g-container              /* 限定宽度 */
.g-container-fluid        /* 不限定宽度 */
.g-row
.g-no-gutters

.g-col-1
.g-col-2
.g-col-3
.g-col-4
.g-col-5
.g-col-6
.g-col-7
.g-col-8
.g-col-9
.g-col-10
.g-col-11
.g-col-12
.g-col-sm-1
.g-col-sm-2
.g-col-sm-3
.g-col-sm-4
.g-col-sm-5
.g-col-sm-6
.g-col-sm-7
.g-col-sm-8
.g-col-sm-9
.g-col-sm-10
.g-col-sm-11
.g-col-sm-12
.g-col-md-1
.g-col-md-2
.g-col-md-3
.g-col-md-4
.g-col-md-5
.g-col-md-6
.g-col-md-7
.g-col-md-8
.g-col-md-9
.g-col-md-10
.g-col-md-11
.g-col-md-12
.g-col-lg-1
.g-col-lg-2
.g-col-lg-3
.g-col-lg-4
.g-col-lg-5
.g-col-lg-6
.g-col-lg-7
.g-col-lg-8
.g-col-lg-9
.g-col-lg-10
.g-col-lg-11
.g-col-lg-12
.g-col-xl-1
.g-col-xl-2
.g-col-xl-3
.g-col-xl-4
.g-col-xl-5
.g-col-xl-6
.g-col-xl-7
.g-col-xl-8
.g-col-xl-9
.g-col-xl-10
.g-col-xl-11
.g-col-xl-12

.g-pull-0
.g-pull-1
.g-pull-2
.g-pull-3
.g-pull-4
.g-pull-5
.g-pull-6
.g-pull-7
.g-pull-8
.g-pull-9
.g-pull-10
.g-pull-11
.g-pull-12

.g-push-0
.g-push-1
.g-push-2
.g-push-3
.g-push-4
.g-push-5
.g-push-6
.g-push-7
.g-push-8
.g-push-9
.g-push-10
.g-push-11
.g-push-12

.g-offset-1
.g-offset-2
.g-offset-3
.g-offset-4
.g-offset-5
.g-offset-6
.g-offset-7
.g-offset-8
.g-offset-9
.g-offset-10
.g-offset-11
```

## Table类
```css
.m-table
.m-table-sm
.m-table-bordered
.m-table-scriped
.m-table-hover
.m-table-inverse
.m-thead-inverse
.m-thead-default
.m-table-responsive
```

## Form类
```css
.m-form
.m-form-inline

.has-warning
.has-success

.form-control-success
.form-control-warning

.form-control
.form-control-file
.form-control-range
.form-control-static
.form-col-label
.form-col-label-sm 
.form-col-label-lg
.form-col-legend

.form-group
.form-text
.form-check
.form-check-inline
.form-check-label
.form-check-input
```

### Input Group类
```css
.m-input-group
.input-group-btn
.input-group-addon
.input-group-control
```

## Button类
```css
.u-btn
.u-btn-link
.u-btn-sm
.u-btn-lg
.u-btn-block

.u-btn-default
.u-btn-primary
.u-btn-secondary

.u-btn-outline-default
.u-btn-outline-primary
.u-btn-outline-secondary
```

## Breadcrumb类
```css
.m-breadcrumb
.breadcrumb-item
```

## 分页类
```css
.m-pagination
.pagination-item
.pagination-link
.m-pagination-lg
.m-pagination-sm
```