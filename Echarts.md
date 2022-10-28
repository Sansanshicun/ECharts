# Echarts

#### ECharts介绍

```html
ECharts，一个使用 JavaScript 实现的开源可视化库，可以流畅的运行在 PC 和移动设备上，兼容当前绝大部分浏览器（IE8/9/10/11，Chrome，Firefox，Safari等），底层依赖矢量图形库ZRender，提供直观，交互丰富，可高度个性化定制的数据可视化图表。
简单的说：
	是一个JS插件
	性能好可流畅运行PC与移动设备
	兼容主流浏览器
	提供很多常用图表，且可定制。
```

#### 常见的数据可视化库

```html
D3.js 目前 Web 端评价最高的 Javascript 可视化工具库(入手难)
ECharts.js 百度出品的一个开源 Javascript 数据可视化库
Highcharts.js 国外的前端数据可视化库，非商用免费，被许多国外大公司所使用
AntV 蚂蚁金服全新一代数据可视化解决方案 等等
Highcharts 和 Echarts 就像是 O
```

#### 快速上手

下载

```html
在 https://www.jsdelivr.com/package/npm/echarts 选择 dist/echarts.js ，点击并保存为
echarts.js 文件。
```

使用步骤

1、引入echarts 插件文件到html页面中 

2、准备一个具备大小的DOM容器

```html
<div id="main" style="width: 600px;height:400px;"></div>
```

3、初始化echarts实例对象

```javascript
var myChart = echarts.init(document.getElementById('main'));
```

4、指定配置项和数据(option)

```javascript
var option = {
	xAxis: {
		type: 'category',
		data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
	},
	yAxis: {
		type: 'value'
	},
	series: [{
		data: [820, 932, 901, 934, 1290, 1330, 1320],
		type: 'line'
	}]
};
```

5、将配置项设置给echarts实例对象

```javascript
myChart.setOption(option);
```

#### Echarts-基础配置

```html
需要了解的主要配置： series xAxis yAxis grid tooltip title legend color
series
	系列列表。每个系列通过 type 决定自己的图表类型
	即图表数据，指定什么类型的图标，可以多个图表重叠。
xAxis：直角坐标系 grid 中的 x 轴
boundaryGap: 坐标轴两边留白策略 true，这时候刻度只是作为分隔线，标签和数据点都会在
			两个刻度之间的带(band)中间。
yAxis：直角坐标系 grid 中的 y 轴
grid：直角坐标系内绘图网格。
title：标题组件
tooltip：提示框组件
legend：图例组件
color：调色盘颜色列表
		数据堆叠，同个类目轴上系列配置相同的 stack 值后 后一个系列的值会在前一个系列的值上相加。
```

```javascript
option = {
	// color设置我们线条的颜色 注意后面是个数组
	color: ['pink', 'red', 'green', 'skyblue'],
	// 设置图表的标题
	title: {
		text: '折线图堆叠123'
	},
	// 图表的提示框组件
	tooltip: {
		// 触发方式
		trigger: 'axis'
	},
	// 图例组件
	legend: {
		// series里面有了 name值则 legend里面的data可以删掉
	},
	// 网格配置 grid可以控制线形图 柱状图 图表大小
	grid: {
		left: '3%',
		right: '4%',
		bottom: '3%',
		// 是否显示刻度标签 如果是true 就显示 否则反之
		containLabel: true
	},
	// 工具箱组件 可以另存为图片等功能
	toolbox: {
		feature: {
			saveAsImage: {}
		}
	},
	// 设置x轴的相关配置
	xAxis: {
		type: 'category',
		// 是否让我们的线条和坐标轴有缝隙
		boundaryGap: false,
		data: ['星期一', '周二', '周三', '周四', '周五', '周六', '周日']
	},
	// 设置y轴的相关配置
	yAxis: {
		type: 'value'
	},
	// 系列图表配置 它决定着显示那种类型的图表
	series: [
		{
			name: '邮件营销',
			type: 'line',
			data: [120, 132, 101, 134, 90, 230, 210]
		},
		
	]
};
```

#### Echarts-社区介绍

在这里可以找到一些基于echart的高度定制好的图表，相当于基于jquery开发的插件，这里是基于 echarts开发的第三方的图表

```html
现在的官网地址：
https://www.makeapie.cn/echarts
```

#### 常见问题 

打不开echarts官网

```html
C:\Windows\System32\drivers\etc下的hosts文件，添加一行：
151.101.2.132 echarts.apache.org
在终端下输入(更新DNS解析缓存)
ipconfig/flushdns
```

