<template>
  <!-- hidden PageHeaderWrapper title demo -->
  <page-header-wrapper :title="false" content="视频创建时间分布">
    <a-card :body-style="{padding: '24px 32px'}" :bordered="false">
      <div>按年份统计</div>
      <div id="year_column" style="width: 700px;height:450px;"></div>
      <div>按月份统计</div>
      <div id="month_column" style="width: 700px;height:450px;"></div>
      <div>按24小时统计</div>
      <div id="hour_column" style="width: 700px;height:450px;"></div>
    </a-card>
  </page-header-wrapper>
</template>

<script>
import * as echarts from 'echarts'

const yearOption = {
    color: ['#3398DB'],
    tooltip: {
        trigger: 'axis',
        axisPointer: { // 坐标轴指示器，坐标轴触发有效
            type: 'shadow' // 默认为直线，可选为：'line' | 'shadow'
        }
    },
    grid: {
        left: '3%',
        right: '4%',
        bottom: '3%',
        containLabel: true
    },
    xAxis: [
        {
            name: '年份',
            type: 'category',
            data: [2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020],
            axisTick: {
                alignWithLabel: true
            }
        }
    ],
    yAxis: [
        {
            name: '数量',
            type: 'value'
        }
    ],
    series: [
        {
            name: '直接访问',
            type: 'bar',
            barWidth: '60%',
            data: [69, 1306, 1956, 1153, 1005, 682, 834, 1116, 1184, 1650, 3153, 3433]
        }
    ]
}
const monthOption = {
    color: ['#52c41a'],
    tooltip: {
        trigger: 'axis',
        axisPointer: { // 坐标轴指示器，坐标轴触发有效
            type: 'shadow' // 默认为直线，可选为：'line' | 'shadow'
        }
    },
    grid: {
        left: '3%',
        right: '4%',
        bottom: '3%',
        containLabel: true
    },
    xAxis: [
        {
            name: '月份',
            type: 'category',
            data: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12],
            axisTick: {
                alignWithLabel: true
            }
        }
    ],
    yAxis: [
        {
            name: '数量',
            type: 'value'
        }
    ],
    series: [
        {
            name: '直接访问',
            type: 'bar',
            barWidth: '60%',
            data: [1444, 1599, 1729, 1616, 1800, 1884, 1264, 1322, 1244, 1045, 1178, 1416]
        }
    ]
}
const hourOption = {
    color: ['#722ed1'],
    tooltip: {
        trigger: 'axis',
        axisPointer: { // 坐标轴指示器，坐标轴触发有效
            type: 'shadow' // 默认为直线，可选为：'line' | 'shadow'
        }
    },
    grid: {
        left: '3%',
        right: '4%',
        bottom: '3%',
        containLabel: true
    },
    xAxis: [
        {
            name: '时',
            type: 'category',
            data: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23],
            axisTick: {
                alignWithLabel: true
            }
        }
    ],
    yAxis: [
        {
            name: '数量',
            type: 'value'
        }
    ],
    series: [
        {
            name: '直接访问',
            type: 'bar',
            barWidth: '60%',
            data: [802, 707, 609, 550, 444, 428, 313, 315, 412, 481, 614, 782, 834, 817, 781, 734, 846, 879, 925, 1061, 1094, 1075, 1047, 991]
        }
    ]
}
export default {
  name: 'SexRatio',
  data () {
    return {
    }
  },
  mounted () {
    this.init_chart()
  },
  methods: {

    init_chart () {
        // 绘制图表。
            echarts.init(document.getElementById('year_column')).setOption(yearOption)
            echarts.init(document.getElementById('month_column')).setOption(monthOption)
            echarts.init(document.getElementById('hour_column')).setOption(hourOption)
    }
  }
}
</script>
