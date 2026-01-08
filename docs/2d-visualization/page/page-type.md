# 画面类型

有2种画面类型：**画面**、**弹窗**。

有以下3个入口，可以创建画面。

**入口1：** 编辑器的默认窗口。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/zCp9FTCKlTuzoahQ_FN9QHu7TxM1339u_gPPf7LCqbQ.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

**入口2：**编辑器的“画面“菜单。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/BKYwJ4DPxWM8yVyMinfGiR0BzAs6pAjHUFNZgDA9mA4.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

**入口3：**在”项目“窗口中，右击”画面“的任意节点。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/MjGw7M-JRVXlErLlCxLtYsw-6cXVEFrehWxAQ99IlTA.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

#### 画面

 填充整个窗口的画面。

###### 画面属性

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/AXvAWjPLHqCqKoDfat2HFhvitUDtxhJZY1G-DgJyzkQ.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

**如何查看画面属性**

1. 点击画面区域的空白处
2. 点击画面的tab页名称

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/ngmUUl0Pe5_vBo77mGJ6ijnXxDFfd4eRixUPfGPqXcY.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

3. 画面缩放后，点击画布之外的灰色区域，下图红框内区域。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/5o4vh9mxWoYzPvvxUxWzbyu64PpCyvrbJ-fidXTsS1k.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

**画面模板**

画面可以直接引用画面模板，将画面模板的样式直接呈现在当前画面上。引用后，在当前画面上不允许对模板内容进行编辑。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/sEQyPAhQOwW6fpQMUEZWlleMpaS4SzB5rqykC_B96tw.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

**分辨率适配**

不同的设备（如计算机、平板电脑、手机等）具有不同的屏幕尺寸和分辨率，如果不进行适当的分辨率适配，可能导致画面在某些设备上出现布局错乱、控件溢出或显示不完整的问题。

设置了分辨率适配后，在不同分辨率的设备上打开画面时，系统会自动识别当前设备的分辨率并自动进行适配和调整。

WAGO VC Hub包含2种分辨率适配方式，详见[known-link]。

| **适配方式**                                                                                                                                                                                               | **描述**                         |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| ![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/f4fjdpQfPmtQN5M2QtPa4peyYX2h0NBU2STAmECaFcA.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM) | 宽高比例保持不变。                |
| ![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/-VtFR_YZRc-moprWoox51rsyU8tX4kiUPAvzRCCPE2U.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM) | 拉伸或缩放画面，使其铺满整个画面。 |

**自定义属性**

除了基本属性设置外，您还可以为画面创建自定义属性。您可以像使用任何其他属性一样使用自定义属性，例如数据绑定、脚本和样式。

自定义属性对于将参数从一个画面传递到另一个画面非常重要。详见[known-link] 。

要配置自定义属性，请执行以下操作：

1. 点击画面空白处。
2. 点击“外观”>“自定义属性”。
3. 单击加号图标以添加一行。
4. 输入自定义属性名称、数据类型、初始值。
5. 添加后自定义属性自动保存。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/sZiAWGizGnjtv5VG-SOkN8_3_57x6vhSdGcumRiMrYw.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

#### 弹窗

 显示在画面之上的窗口。在运行页面，弹窗可以拖动进行位置变更。但只能在当前窗口内拖动，不可以拖动到窗口之外的区域。

###### 弹窗属性

弹窗比画面多了标题栏设置的属性。可以根据特定的需求，在弹窗的外观属性中设置弹窗的标题栏样式。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/hu7BzuUeObVavg06xk8DDSAp6mZHoPaRgjGXej9gTVg.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

**如何查看弹窗属性**

1. 点击画面区域的空白处
2. 点击画面的tab页名称

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/VrQpUi9YF664beZ7GPsTSN1x7dEAzABY9PShf5jYLmc.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

3. 点击画布之外的灰色区域。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/fhdDDYGQz2Q0h-JYQBYQ7q8Vo0ROEZr1yRgbVj7cFiM.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

###### 弹窗位置

可以指定一个特定的位置来打开弹窗。详见[known-link] 。

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/ZUf43kLgy3-60gQ0JmqXK3h6_bq-tJFiFuWVma0ULgc.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

弹窗样式示例：  

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/dIJo5p0zCFz3EMCYFvzj-OfXNr4ZH-gh8FYt21BNsbA.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)

![img](https://docs.wagoscada.cn/wiki/api/wiki/editor/QHXVK91b/NUuVweaH/resources/BXAJWKCC61vN3jpMBKWhOh2SxG2x0L-mzNw3Cjtmz1A.png?token=W.8PwIf8iZW-yi6TSrgz_nhk639ELGuFWSlz5sKsCfY9YeI-uaSGbZGrtkcdvzFtM)



