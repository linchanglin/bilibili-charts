<template>
  <!-- hidden PageHeaderWrapper title demo -->
  <page-header-wrapper :title="false" content="分析b站的视频类型">
    <a-card :body-style="{padding: '24px 32px'}" :bordered="false">
      <div id="main" style="width: 700px;height:450px;"></div>
      <div id="column" style="width: 700px;height:450px;"></div>
    </a-card>
  </page-header-wrapper>
</template>

<script>
import * as echarts from 'echarts'
const option = {
    title: {
        text: 'b站视频类型分布',
        // subtext: '纯属虚构',
        left: 'center'
    },
    tooltip: {
        trigger: 'item',
        formatter: '{a} <br/>{b} : {c} ({d}%)'
    },
    legend: {
        orient: 'vertical',
        left: 'left',
        data: ['游戏', '动画', '音乐', '生活', '娱乐', '舞蹈', '知识', '番剧', '鬼畜', '影视', '数码', '纪录片', '时尚', '国创', '公告', '电视剧']
    },
    series: [
        {
            name: '用户性别',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
                { 'name': '游戏', 'value': 25242 },
                { 'name': '动画', 'value': 10439 },
                { 'name': '音乐', 'value': 7389 },
                { 'name': '生活', 'value': 5962 },
                { 'name': '娱乐', 'value': 2617 },
                { 'name': '舞蹈', 'value': 1194 },
                { 'name': '知识', 'value': 1049 },
                { 'name': '番剧', 'value': 996 },
                { 'name': '鬼畜', 'value': 668 },
                { 'name': '影视', 'value': 351 },
                { 'name': '数码', 'value': 227 },
                { 'name': '纪录片', 'value': 96 },
                { 'name': '时尚', 'value': 87 },
                { 'name': '国创', 'value': 46 },
                { 'name': '公告', 'value': 2 },
                { 'name': '电视剧', 'value': 2 }
            ],
            emphasis: {
                itemStyle: {
                    shadowBlur: 10,
                    shadowOffsetX: 0,
                    shadowColor: 'rgba(0, 0, 0, 0.5)'
                }
            }
        }
    ]
}

const optionColumn = {
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
            type: 'category',
            data: ['游戏', '动画', '音乐', '生活', '娱乐', '舞蹈', '知识', '番剧', '鬼畜', '影视', '数码', '纪录片', '时尚', '国创', '公告', '电视剧'],
            axisTick: {
                alignWithLabel: true
            }
        }
    ],
    yAxis: [
        {
            type: 'value'
        }
    ],
    series: [
        {
            name: '直接访问',
            type: 'bar',
            barWidth: '60%',
            data: [25242, 10439, 7389, 5962, 2617, 1194, 1049, 996, 668, 351, 227, 96, 87, 46, 2, 2]
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
            echarts.init(document.getElementById('main')).setOption(option)
            echarts.init(document.getElementById('column')).setOption(optionColumn)
    }
  }
}
</script>
