<template>
  <!-- hidden PageHeaderWrapper title demo -->
  <page-header-wrapper :title="false" content="分析b站的性别比例">
    <a-card :body-style="{padding: '24px 32px'}" :bordered="false">
      <div id="main" style="width: 700px;height:450px;"></div>
    </a-card>
  </page-header-wrapper>
</template>

<script>
import * as echarts from 'echarts'
const option = {
    title: {
        text: 'b站性别比例',
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
        data: ['男', '女', '保密']
    },
    series: [
        {
            name: '用户性别',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
                { value: 470, name: '男' },
                { value: 137, name: '女' },
                { value: 9592, name: '保密' }
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
    }
  }
}
</script>
