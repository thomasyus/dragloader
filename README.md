dragloader.js
==========

dragloader.js是一个面向移动Web开发的JavaScript库，帮助开发者在使用页面原生滚动时，模拟上/下拉手势，实现Pull Request操作。

在移动设备上，一般会使用 drag down 手势实现加载最新

![dragdown](https://raw.github.com/maxzhang/dragloader/master/examples/dragdown.gif)

使用 drag up 手势实现加载更多

![dragup](https://raw.github.com/maxzhang/dragloader/master/examples/dragup.gif)

dragloader样例需运行在 Smart Phone/Pad 上，扫描二维码：

![dragloader.js demo](example/qrcode.png)


**Note：目前dragloader.js在iOS下运行不是很稳定，上拉操作会有闪跳现象，Android下表现正常。**


## Options

**disableDragDown : Boolean**

true禁用下拉操作


**disableDragUp : Boolean**
true禁用上拉操作


**dragDownThreshold : Number**

下拉区域临界值，超过这个值状态将由“default”变为“perpare”，默认80


**dragUpThreshold : Number**

上拉区域临界值，超过这个值状态将由“default”变为“perpare”，默认80


**dragDownRegionCls : String**

下拉区域样式


**dragUpRegionCls : String**

上拉区域样式


**dragDownHelper( String status )**

下拉区域html更新函数，需要根据不同状态返回html碎片，status取值范围：'default'、'prepare'、'load'


**dragUpHepler( String status )**

上拉区域html更新函数，需要根据不同状态返回html碎片，status取值范围：'default'、'prepare'、'load'


*preventDragHelper : Boolean**

禁用dragHelper，由外部控制dragHelper


**beforeDrag() : Boolean**

drag开始回调函数，返回false时，本次drag动作将失效


**onDragDownDefault()**

当下拉区域drag状态更新为'default'时触发


**onDragDownPrepare()**

当下拉区域drag状态更新为'prepare'时触发


**onDragDownLoad()**

当下拉区域drag状态更新为'load'时触发


**onDragUpDefault()**

当上拉区域drag状态更新为'default'时触发


**onDragUpPrepare()**

当上拉区域drag状态更新为'prepare'时触发


**onDragUpLoad()**

当上拉区域drag状态更新为'load'时触发


## Methods

**setDragDownDisabled(Boolean disabled)**

设置下拉区域禁用状态

**setDragUpDisabled(Boolean disabled)**

设置上拉区域禁用状态

**reset()**

重置drag状态。

无论何时，必须由业务功能主动调用reset()接口，以还原状态。比如在onDragDownLoad()回调中使用ajax加载数据时，在ajax的回调函数中应当调用reset()重置drag状态。如果不重置，drag操作将失效.
