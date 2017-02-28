# qianka-et-ad-theme
> element component theme for qianka platform.


## Installation
```shell
npm i qianka-et-ad-theme -S
```

## Usage

Use Sass Or postcss-import
```css
@import 'qianka-et-ad-theme';
```

Or Use webpack
```javascript
import 'qianka-et-ad-theme';
```

Or
```html
<link rel="stylesheet" href="path/to/node_modules/qianka-et-ad-theme/lib/index.css">
```

##  Import your need
```javascript
import 'qianka-et-ad-theme/lib/input.css';
import 'qianka-et-ad-theme/lib/select.css';
或见deploy中的描述
// ...
```

## Build

```shell
gulp build
```

执行build以后，会在lib目录下生成编译后的文件

### Deploy with files

仅需lib目录下的index.css和字体文件目录fonts

## 组件

### Dialog 对话框

<table>
        <tr>
            <th>参数</th>
            <th>说明</th>
            <th>可选值</th>
            <th>qt主题增加值</th>
        </tr>
        <tr>
            <td>size</td>
            <td>Dialog 的大小</td>
            <td>tiny/small/large/full</td>
            <td>fixed390</td>
        </tr>
        <tr>
            <td>说明</td>
            <td></td>
            <td>  tiny 30%;
                  small: 50%;
                  large: 90%;
                  full代表铺满屏幕</td>
            <td>
                宽度固定为390px
            </td>
        </tr>
    </table>

   原el组件只能支持宽度自由伸缩
   ```
  <el-dialog title="删除" v-model="dialogVisible" size="tiny" top="38%">
        ...
  </el-dialog>
   ```
   qk主题的固定长度390px的使用
   ```
    <el-dialog title="删除" v-model="dialogVisible" size="fixed390" top="38%">
        ...
  </el-dialog>
   ```

   关于对话框高度、大小、宽高比的已知问题：

   要求：对话框宽度固定为390px，高度固定为202px，或者保持在接近这个视觉的宽高比。

   dialog对话框组件的宽度和高度是无法同时设置为一个固定值的，因为dialog的对话框实际的大小由body区域内容决定,对话框整体高度 = 头部高度+内容高度+脚注高度+外围边距。所以目前fixed390对话框的高度202px是由脚注高度顶部边距由25px调整为12px而拼凑出来的。如果内容区域，有多行文字内容，而不是一行内容，则整个对话框高度自然会增长。那么那个时候，由于高度固定为390px，而宽度增加，长和宽的比例又会发生变化。所以，回过头来看，产品会怎么看这个问题呢？

   参照el现有的设计模式的直接启发，如果今后对话框类型还会增加，倾向与增加比例型设定的对话框。在现有30%、50%、90%外增加几个类型来适应需求。

### Button 按钮
