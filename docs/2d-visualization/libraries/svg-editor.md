# SVG编辑器

SVG编辑器用于对图库中的SVG图形进行编辑，包括背景色，边框色，可见性，位置，尺寸，文本等。

#### 如何打开SVG编辑器

有如下4种方式，可以打开SVG编辑器。

- 在图库中，双击SVG格式的图片
- 在图库的SVG格式图片上右击鼠标，在菜单中点击”编辑“
- 在画面上双击SVG格式的图片
- 在画面中的SVG格式图片上右击鼠标，在菜单中点击”编辑“

SVG编辑器界面如下：

![alt text](24.png)

#### 支持编辑的元素类型

- rect
- circle
- ellipse
- line
- polyline
- polygon
- path
- text
- group

不支持编辑的元素类型，在对象窗口中会显示为灰色。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/5u2tGWTDPofUCLbzV23GZCcxpc_q14ghO8dY_plbIyQ.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

#### 元素属性

###### rect

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/mPa3QHgrKqikAz-WLAN4Br51kBd-8_5Qid-P4HAN18c.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**                         |
|----------|----------------------------------|
| 名字     | 此控件的名称。                    |
| X        | 控件左侧距画布左侧的距离，单位px。 |
| Y        | 控件顶部距画布顶部的距离，单位px。 |
| W        | 控件的宽度，单位px。               |
| H        | 控件的高度，单位px。               |
| RX       | 矩形水平方向上圆角的半径。        |
| RY       | 矩形垂直方向上圆角的半径。        |
| 填充     | 矩形的填充色。                    |
| 边框颜色 | 矩形的边框颜色。                  |
| 边框粗细 | 矩形的边框粗细。                  |

###### circle

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/2y_LIiuZnNBqBcJu7y82BdC6peVr51b__xInSX5FdKo.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**                       |
|----------|--------------------------------|
| 名字     | 此控件的名称。                  |
| CX       | 圆心在水平方向上的位置，单位px。 |
| CY       | 圆心在垂直方向上的位置，单位px。 |
| R        | 圆的半径，单位px。               |
| 填充     | 控件的填充色。                  |
| 边框颜色 | 控件的边框颜色。                |
| 边框粗细 | 控件的边框粗细。                |

###### ellipse

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/2PvFH1FPH6wspJqgnMoq7c2yuCowy78QjPj_JtUvzFU.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**                             |
|----------|--------------------------------------|
| 名字     | 此控件的名称。                        |
| CX       | 椭圆的圆心在水平方向上的位置，单位px。 |
| CY       | 椭圆的圆心在垂直方向上的位置，单位px。 |
| RX       | 椭圆在水平方向上的半径，单位px。       |
| RY       | 椭圆在垂直方向上的半径，单位px。       |
| 填充     | 控件的填充色。                        |
| 边框颜色 | 控件的边框颜色。                      |
| 边框粗细 | 控件的边框粗细。                      |

###### line

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/4jqHrhij14XsIo3QFBYaNTExq3Z9Nfo-xVMVoBIIm_E.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**                               |
|----------|----------------------------------------|
| 名字     | 此控件的名称。                          |
| X1       | 直线起始点的水平（X 轴）坐标，单位px。     |
| Y1       | 直线起始点的垂直方向（Y 轴）坐标，单位px。 |
| X2       | 直线终点的水平（X 轴）坐标，单位px。       |
| Y2       | 直线终点的垂直方向（Y 轴）坐标，单位px。   |
| 边框颜色 | 控件的边框颜色。                        |
| 边框粗细 | 控件的边框粗细。                        |

###### polyline

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/SdszDdAESxBs6eJNf7-wJc_L9Fd-OrPQRiShWf29jik.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**   |
|----------|-----------|
| 名字     | 此控件的名称。|
| 点       | 一串坐标点，其形式为   x1， y1   x2， y2   x3， y3   …  会从第一个点开始，依次连接后面的点，形成一条折线。 |
| 边框颜色 | 控件的边框颜色。|
| 边框粗细 | 控件的边框粗细。|

###### polygon

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/_zNrG5dfEYdX9FmSPu5apWeO9Ht1Pvty67Esb3zzCPg.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**    |
|----------|-------------|
| 名字     | 此控件的名称。|
| 点       | 一串坐标点，其形式为   x1， y1   x2， y2   x3， y3   …  会从第一个点开始，依次连接后面的点，和 polyline 不同，polygon 会自动把最后一个点连回第一个点，形成闭合区域。 |
| 填充     | 控件的填充色。 |
| 边框颜色 | 控件的边框颜色。  |
| 边框粗细 | 控件的边框粗细。|

###### path

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/CzR2RiPjyj_KQNMTj2ZqzksB6ws7_kOOEhtk2P_cILs.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**  |
|----------|---------------|
| 名字     | 此控件的名称。 |
| D        | “D”属性是一个包含一系列指令和坐标值的字符串。这些指令和坐标值决定了路径的形状。  常见的指令有：  M：移动到指定位置。M10,10：移动到（10，10）点。  L：绘制一条线至指定位置。L100，100：从（10，10）点绘制一条线至（100，100）点。  C：绘制一个三次贝塞尔曲线。C40，10， 65，10， 95，50：绘制一个带有控制点（40，10）和（65，10）以及终点（95，50）的三次贝塞尔曲线。  S：绘制一条平滑的贝塞尔曲线。S150，150， 200，100：绘制一条带有自动计算的控制点并以（200，100）点结束的平滑三次贝塞尔曲线。  Q：绘制一个二次贝塞尔曲线。Q50，10， 90，50：绘制一个带有控制点（50，10）和终点（90，50）的二次贝塞尔曲线。  T：绘制一条平滑的二次贝塞尔曲线。T150，150：绘制一条带有自动计算的控制点并以（150，150）点结束的平滑二次贝塞尔曲线。  Z：闭合路径（返回起始点）。Z：闭合路径并返回起始点。 |
| 填充     | 控件的填充色。|
| 边框颜色 | 控件的边框颜色。 |
| 边框粗细 | 控件的边框粗细。 |

###### text

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/jSsDFnFV5Jh10Y4A5qAL5YaeosdkhiB2TnEl2DZPZYs.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**                                         |
|----------|--------------------------------------------------|
| 名字     | 此控件的名称。                                    |
| X        | 控件左侧距画布左侧的距离，单位px。                 |
| Y        | 控件顶部距画布顶部的距离，单位px。                 |
| 文本     | 文本内容。                                        |
| 字体     | 设置字体样式，字体大小，加粗，倾斜，下划线，字体颜色。 |

###### group

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/0G2Gg2rVtNNe01w5T0QrnlLEaXMow81R3try4C_pt5U.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**属性**

| **名称** | **描述**      |
|----------|---------------|
| 名字     | 此控件的名称。 |

#### 示例

**示例1：**手动修改SVG图片中元素的颜色。

1. 双击图库中的一张svg图片，例如下图的A.svg

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/40yXx9sDJdkxakIxGyScQ1T7LsnCaRpd2UsCm80rMQE.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

2. 在SVG编辑器中的对象窗口中，选中一个path元素

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/xjxFpop2-_vTVyOcK8_ZxujLVyKSysKTg8ukk__ecIQ.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

3. 将填充色修改为绿色并另存为A1

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/btuUIEI6c40Cc9LUNnZoptc70htL6I4Jmn5c5QOLyqQ.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

4. 在图库中查看保存后的图片，显示修改后的效果。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/4fFA7MQamW6ebbkT1ldnDt6Hqn8fhJBRj4zt0wOnuUE.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**示例2：**通过属性绑定，动态改变SVG图片中元素的颜色。

1. 从图库中添加一个SVG图片到画面上

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/UC6p_u-yCliRJdS0GOP1Dyw7VnzBC0ZBn-bnbjdWBMc.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

2. 双击该图片，打开SVG编辑器
3. 在SVG编辑器内，选择一个元素，点击其填充色的绑定按钮

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/2ikF16k23zku-OlsrBV2merDxFcgbOUQ1ziMsBmLrm8.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

4. 绑定一个数值型变量，并设置如下颜色区间。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/_BMduWjX6-m33lXk8SeUioousSx-hvGtFTEHi21YxNc.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

5. 保存后关闭SVG编辑器，点击画面的预览按钮，查看图片的预览效果，会发现随着变量值的变化，SVG图片呈现不同的颜色效果。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/aylJEsOd2nVMq_XXk4rxMxmjGncweOo3LftmT0hQ1yM.gif?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

**示例3：**通过属性SVG图片的自定义属性，反应不同设备的运行状态。

1. 从图库中添加一个SVG图片到画面上，该图片用作反应设备运行状态的指示灯

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/p_cK0AGOWoSzJevOxUx6EX00GdFxNC_-G2CjvdBHZu4.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

2. 双击该图片，打开SVG编辑器
3. 在SVG编辑器内，点击图片的根节点，为其添加一个自定义属性motorNo,用作设备编号

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/j6_7O6dORZnvjfCm19XH-F1HEDcVqOEKVUa9W1O-aIk.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

4. 点击元素，例如上图的path1, 为其填充色绑定动态属性，用于显示Motor1,Motor2，Motor3的运行状态，并为状态值设置对应的填充色。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/wmrEFbQhAfBfc9fzHF-Xet6t6z3sHBQyyeOapPWP4F0.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

5. 保存并关闭SVG编辑器，在画面上添加一个下拉框，将其下拉内容的**文本**和**值**设置为下图所示内容。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/FqXQIngBsPBA_tkwjter_PsTrl_BLfEQRvESFW95rpk.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

6. 将SVG的自定义属性绑定到下拉框的selectedValue属性。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/-TtmiwfWAjTXuLGAQp-BTv0hKo4Wtfqeu16BqQcyCL4.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/xg9pbLMDA5Rb-i71lT5bmgTG8yTSpLACVR9wt2kujUw.png?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)

7. 点击预览按钮，在运行页面，切换下拉选项时，SVG图片会根据对应设备的运行状态，显示不同的颜色。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/9BjnANqS/resources/H827lC0KlnqvPGrSTjvnIQze4_O5hNbGzqgbx4QF5jQ.gif?token=W.US0T3vvK7NUv_KvxFqabbnfrhUK_NppIyDc9oiLYQqWXn8_nZUr1atfmoep9vBs)



