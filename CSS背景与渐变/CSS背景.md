# CSS背景与渐变
## 背景样式
### 背景裁切
`background-clip` 属性
- `border-box` : 应用到边框
- `padding-box` : 不含边框，包括内边距
- `content-box` : 应用到内容区域

```CSS
background-clip: content-box;
```
****
### 背景重复
`background-repeat` 属性：用于设置背景重复的规则
- `no-repeat` : 不重复
- `repeat` : 水平、垂直重复
- `repeat-x` : 水平重复
- `repeat-y` : 垂直重复
- `space` : 背景图片均匀分布

```CSS
background-repeat: repeat-y;
```
****
### 背景滚动
`background-attachment` 属性：用于设置在页面滚动时的图片处理方式
- `scroll` : 背景滚动
- `fixed` : 背景固定

```CSS
background-attachment: fixed;
```
****
### 背景位置
`background-position` 属性：用于设置背景图片的水平、垂直定位
- `left` : 左对齐
- `right` : 右对齐
- `center` : 居中对齐
- `bottom` : 底部对齐
- `top` : 顶部对齐

**居中对齐**
```CSS
background-position: center;
或
background-position: 50% 50%;
```
**水平居右，垂直居中**
```CSS
background-position: right center;
或
background-position: 100% 50%;
```
**使用具体数值定义**
```CSS
background-position: 100px 100px;
```
****
### 背景尺寸
`background-size` 属性
- `cover` : 背景完全覆盖，可能会有背景溢出
- `contain` : 图片不溢出的放在容器中，可能会漏出部分区域

**指定数值定义宽高尺寸**
```CSS
background-size: 50% 100%;
```
**宽度固定高度自适应**
```CSS
background-size: 50% auto;
```
****
### 多个背景
**后定义的背景置于底层**
```CSS
background-image: url(xj-small.png), url(bg.png);
```
**多属性定义**
```CSS
background-image: url(xj-small.png), url(bg.png);
background-repeat: no-repeat;
background-position: top left, right bottom;
```
****
### 组合设置
可以使用一条指令设置背景
```CSS
background: red url(xj-small.png) no-repeat right 50% fixed;
```
****
## 颜色渐变
### 线性渐变
**渐变可以设置角度和方向**
```CSS
/* 角度渐变 */
background: linear-gradient(30deg, red, green);
/* 向右渐变 */
background: linear-gradient(to right, red, green);
```
<div style="height: 20px;background: linear-gradient(to right, red, green)"></div>

****
### 径向渐变
```CSS
/* 设置渐变 */
background: radial-gradient(red, blue, green);
/* 设置渐变的宽度和高度 */
background: radial-gradient(100px 200px, red, blue, green);
/* 设置渐变方向 */
background: radial-gradient(at center left, red, blue);
```

****
### 标识位
颜色未指定标识位时，颜色会平均分布
红色与蓝色在50% ~ 60%之间会发生激变
```CSS
background: linear-gradient(45deg, red 50%, blue 0%);
```
<div style="height: 20px; background: linear-gradient(45deg, red 50%, blue 60%);"></div>

标识位相同时没有过渡效果
```CSS
background: linear-gradient(45deg, red 0,red 50%, blue 50%);
```
<div style="height: 20px; background: linear-gradient(45deg, red 0,red 50%, blue 50%);"></div>

CSS径向标识位绘制太阳
```CSS
background: radial-gradient(red 0, yellow 30%, black 70%, black 100%);
```
<div style="width: 100px; height: 100px; background: radial-gradient(red 0, yellow 30%, black 70%, black 100%);"></div>

****