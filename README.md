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

   已知问题：dialog对话框组件的宽度和高度是无法同时设置为一个固定值的，因为dialog的对话框实际的大小由body区域内容决定,对话框高度 = 头部高度+内容高度+脚注高度+外围边距。
