<template>
  <!-- hidden PageHeaderWrapper title demo -->
  <page-header-wrapper :title="false" content="分析b站的性别比例">
    <a-card :body-style="{padding: '24px 32px'}" :bordered="false">
      <div id="main" style="width: 700px;height:450px;"></div>
      <div>刚开始发现摩羯座的特别多，后来发现很多人的生日写的1月1日，剔除1-1日后的分布图如下</div>
      <div id="column" style="width: 700px;height:450px;"></div>
    </a-card>
  </page-header-wrapper>
</template>

<script>
import * as echarts from 'echarts'
const option = {
    title: {
        text: 'b站星座比例',
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
        data: ['白羊座', '金牛座', '双子座', '巨蟹座', '狮子座', '处女座', '天秤座', '天蝎座', '射手座', '魔羯座', '水瓶座', '双鱼座']
    },
    series: [
        {
            name: '用户性别',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [

                { value: 47, name: '白羊座' },
                { value: 40, name: '金牛座' },
                { value: 42, name: '双子座' },

                { value: 55, name: '巨蟹座' },
                { value: 42, name: '狮子座' },
                { value: 43, name: '处女座' },

                { value: 69, name: '天秤座' },
                { value: 54, name: '天蝎座' },
                { value: 58, name: '射手座' },

                { value: 522, name: '魔羯座' },
                { value: 60, name: '水瓶座' },
                { value: 59, name: '双鱼座' }

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
            data: ['白羊座', '金牛座', '双子座', '巨蟹座', '狮子座', '处女座', '天秤座', '天蝎座', '射手座', '魔羯座', '水瓶座', '双鱼座', '01-01'],
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
            data: [47, 40, 42, 55, 42, 43, 69, 54, 58, 39, 60, 59, 483]
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
