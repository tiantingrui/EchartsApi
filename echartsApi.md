Echarts 配置项

> 这里收录的是笔者本人工作实际开发中用到的相关配置，做记录总结!

- yAxisIndex 做双Y轴功能

> series 中指定字段yAxisIndex来指定应用那个Y轴，计数默认是从0开始



```js
series: [
  {
    name: '销量',
    type: 'bar',
    data: datas1,
    yAxisIndex:0,
    //警示线
    markLine :{...}
  },
  {
    name: '百分比',
    type: 'line',
    data: datas2,
    yAxisIndex:1, // 这里指定的是第二条Y轴
    //警示线
    markLine :{...}
  }
]
```



- markLine 标识线、警示线

> 实际开发中会遇到添加标识线来做划分，更利于用户体验



```js
// 一种实际的开发场景，对于双Y轴添加对应的标识线
series: [
  {
    name: '销量',
    type: 'bar',
    data: datas1,
    yAxisIndex:0,
    //警示线
    markLine :{...}
  },
  {
    name: '百分比',
    type: 'line',
    data: datas2,
    yAxisIndex:1,
    //警示线
    markLine :{...}
  }
]
```



```js
// markline的基本配置，可根据官网详细api来达到想要的效果
markline: {
  symbol: ['none', 'none'],
    data: [
      {
        name: '出票平均数',
        yAxis: markLineNum,
        lineStyle: {
          normal: {
            color: '#22C3AA',
            width: 2
          }
        }
      }
    ]
}
```



- axisLine 坐标轴线属性

- - 记录修改X轴，Y轴的颜色以及多个X轴和Y轴的颜色做区分



```js
// 这里改变的是双Y轴情况下改变其中一个坐标轴的颜色
yAxis: [
  {
    type: 'value',
    name: '收益率百分比(%)',
    axisLabel: {
      show: true,
      interval: 'auto',
      formatter: '{value} %'
    },
    axisLine: {
      lineStyle: {
        color: '#ff6700',
        width: 3
      }
    },
    show: true
  },
]
```

+ areaStyle  给折线加阴影区域

```js
// 在series 对应的折线加阴影面积
series: {
    name: taskName,
    type: 'line',
    data: this.taskRateData,
    smooth: true,
    areaStyle: { // 加阴影区域
        // color: 'blue',
        normal: {
            // color: 'blue'
        }
    },
    hoverAnimation: true,
    itemStyle: {
        normal: {
            color: '#D95850', // 折点颜色
                lineStyle: {
                    color: '#D95850' // 折线颜色
                }
        }
    }
}
```

