<template>
  <!-- hidden PageHeaderWrapper title demo -->
  <page-header-wrapper :title="false" content="分析b站的视频类型">
    <a-card :body-style="{padding: '24px 32px'}" :bordered="false">

      <a-row :gutter="[16,16]" v-for="(followerUser,index) in topFollowerUsers" :key="followerUser.mid">
        <div style="padding-left: 8px">粉丝数第{{ index + 1 }}名</div>
        <a-col :span="8">
          <a-card hoverable style="width: 240px">
            <img
              v-if="index === 0"
              slot="cover"
              alt="example"
              src="~@/assets/imgs/1.jpg"
            />
            <img
              v-if="index === 1"
              slot="cover"
              alt="example"
              src="~@/assets/imgs/2.jpg"
            />
            <img
              v-if="index === 2"
              slot="cover"
              alt="example"
              src="~@/assets/imgs/3.jpg"
            />
            <img
              v-if="index === 3"
              slot="cover"
              alt="example"
              src="~@/assets/imgs/4.jpg"
            />
            <img
              v-if="index === 4"
              slot="cover"
              alt="example"
              src="~@/assets/imgs/5.jpg"
            />
            <a-card-meta>
              <template slot="description">
                <div>名字：{{ followerUser.name }}</div>
                <div>性别：{{ followerUser.sex }}</div>
                <div>宣言：{{ followerUser.sign }}</div>
                <div>关注数：{{ followerUser.following }}</div>
                <div>粉丝数：{{ followerUser.follower }}</div>
                <div>获赞数：{{ followerUser.likes }}</div>
              </template>
            </a-card-meta>
          </a-card>
        </a-col>
        <a-col :span="16">
          <div :id="index+1" style="width: 700px;height:450px;"></div>
        </a-col>
      </a-row>

    </a-card>
  </page-header-wrapper>
</template>

<script>
import * as echarts from 'echarts'
// import { topFollowerUsers, topLikesUsers } from './top-user-data'
const option1 = {
    title: {
        text: '视频类型分布',
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
        data: ['游戏', '生活']
    },
    series: [
        {
            name: '用户性别',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
                { 'name': '游戏', 'value': 3 },
                { 'name': '生活', 'value': 1 }
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
const option2 = {
    title: {
        text: '视频类型分布',
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
        data: ['番剧']
    },
    series: [
        {
            name: '用户性别',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
                { 'name': '番剧', 'value': 2 }
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
const option3 = {
    title: {
        text: '视频类型分布',
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
        data: ['音乐', '游戏', '数码', '生活']
    },
    series: [
        {
            name: '用户性别',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
                { 'name': '音乐', 'value': 49 },
                { 'name': '游戏', 'value': 4 },
                { 'name': '数码', 'value': 1 },
                { 'name': '生活', 'value': 1 }
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
const option4 = {
    title: {
        text: '视频类型分布',
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
        data: ['游戏', '番剧', '动画', '音乐']
    },
    series: [
        {
            name: '用户性别',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
                { 'name': '游戏', 'value': 10 },
                { 'name': '番剧', 'value': 9 },
                { 'name': '动画', 'value': 4 },
                { 'name': '音乐', 'value': 1 }
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
const option5 = {
    title: {
        text: '视频类型分布',
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
        data: ['游戏', '数码', '动画', '音乐']
    },
    series: [
        {
            name: '用户性别',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
                { 'name': '游戏', 'value': 10 },
                { 'name': '数码', 'value': 4 },
                { 'name': '动画', 'value': 1 },
                { 'name': '音乐', 'value': 1 }
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
        topFollowerUsers: [
            { 'mid': 553, 'name': '麻奥', 'sex': '保密', 'img': '@/assets/logo.svg', 'face': 'http://i1.hdslb.com/bfs/face/11d2cd814b17ef6738d910102a085a3418e508f1.jpg', 'sign': '没有飞天小裤裤和天麻还想要钱？！w(ﾟДﾟ)w', 'rank': 10000, 'level': 5, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '', 'coins': 0, 'fans_badge': true, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 217, 'name': 'citrus', 'image': 'http://i1.hdslb.com/bfs/face/f2d3a85b611eb2ef13cb64415187e3e9fd487ec8.png', 'expire': 0, 'image_enhance': 'http://i1.hdslb.com/bfs/face/f2d3a85b611eb2ef13cb64415187e3e9fd487ec8.png' }, 'nameplate': { 'nid': 40, 'name': '老司机', 'image': 'http://i1.hdslb.com/bfs/face/88013f24627e8db0ee3261adf7c8a7d0077c4d4e.png', 'image_small': 'http://i0.hdslb.com/bfs/face/075ed5043bdabcbe4f8bc6d730d630cb4b6ade13.png', 'level': '高级勋章', 'condition': '直播主播等级>=20级' }, 'is_followed': false, 'top_photo': 'http://i0.hdslb.com/bfs/space/44873d3568bdcb3d850d234e02a19602972450f1.png', 'theme': {}, 'sys_notice': {}, 'following': 106, 'whisper': 0, 'black': 0, 'follower': 1272, 'archive': { 'view': 3188 }, 'article': { 'view': 0 }, 'likes': 107 },
            { 'mid': 257, 'name': '星界poi', 'sex': '保密', 'img': '~@/assets/imgs/2.jpg', 'face': 'http://i1.hdslb.com/bfs/face/503535bac31f65db67c93140b0e9c24955a8bfb7.jpg', 'sign': 'ammp 忙成狗', 'rank': 10000, 'level': 5, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '', 'coins': 0, 'fans_badge': false, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 0, 'name': '', 'image': '', 'expire': 0, 'image_enhance': '' }, 'nameplate': { 'nid': 7, 'name': '见习搬运工', 'image': 'http://i1.hdslb.com/bfs/face/8478fb7c54026cd47f09daa493a1b1683113a90d.png', 'image_small': 'http://i1.hdslb.com/bfs/face/50eef47c3a30a75659d3cc298cfb09031d1a2ce5.png', 'level': '普通勋章', 'condition': '转载视频投稿通过总数>=10' }, 'is_followed': false, 'top_photo': 'http://i2.hdslb.com/bfs/space/cb1c3ef50e22b6096fde67febe863494caefebad.png', 'theme': {}, 'sys_notice': {}, 'following': 82, 'whisper': 0, 'black': 0, 'follower': 788, 'archive': { 'view': 2263490 }, 'article': { 'view': 0 }, 'likes': 131 },
            { 'mid': 27251, 'name': '花戶小鳩', 'sex': '男', 'img': '~@/assets/imgs/3.jpg', 'face': 'http://i1.hdslb.com/bfs/face/8f13945afada2d5c2894ba5f9aa4ed224d5841e7.jpg', 'sign': 'cnm', 'rank': 10000, 'level': 5, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '11-16', 'coins': 0, 'fans_badge': false, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 252, 'name': '春原庄的管理人小姐', 'image': 'http://i2.hdslb.com/bfs/face/14738b92760b90675d4bf35dd059b0a666113bae.png', 'expire': 0, 'image_enhance': 'http://i2.hdslb.com/bfs/face/14738b92760b90675d4bf35dd059b0a666113bae.png' }, 'nameplate': { 'nid': 7, 'name': '见习搬运工', 'image': 'http://i2.hdslb.com/bfs/face/8478fb7c54026cd47f09daa493a1b1683113a90d.png', 'image_small': 'http://i2.hdslb.com/bfs/face/50eef47c3a30a75659d3cc298cfb09031d1a2ce5.png', 'level': '普通勋章', 'condition': '转载视频投稿通过总数>=10' }, 'is_followed': false, 'top_photo': 'http://i0.hdslb.com/bfs/space/b4cd9d75cfcb5bef7b10a4de6802f1b0246db736.png', 'theme': {}, 'sys_notice': {}, 'following': 114, 'whisper': 0, 'black': 0, 'follower': 346, 'archive': { 'view': 399625 }, 'article': { 'view': 0 }, 'likes': 1354 },
            { 'mid': 16617, 'name': '藤堂妖里卡', 'sex': '保密', 'img': '~@/assets/imgs/4.jpg', 'face': 'http://i2.hdslb.com/bfs/face/602e2415772c176f3c21ae6feed83208fc84fe85.jpg', 'sign': '再看吸你血哦！ξ(Ծ‸Ծ)ξ', 'rank': 10000, 'level': 5, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '', 'coins': 0, 'fans_badge': false, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 0, 'name': '', 'image': '', 'expire': 0, 'image_enhance': '' }, 'nameplate': { 'nid': 7, 'name': '见习搬运工', 'image': 'http://i2.hdslb.com/bfs/face/8478fb7c54026cd47f09daa493a1b1683113a90d.png', 'image_small': 'http://i0.hdslb.com/bfs/face/50eef47c3a30a75659d3cc298cfb09031d1a2ce5.png', 'level': '普通勋章', 'condition': '转载视频投稿通过总数>=10' }, 'is_followed': false, 'top_photo': 'http://i1.hdslb.com/bfs/space/cb1c3ef50e22b6096fde67febe863494caefebad.png', 'theme': {}, 'sys_notice': {}, 'following': 209, 'whisper': 0, 'black': 0, 'follower': 117, 'archive': { 'view': 107883 }, 'article': { 'view': 0 }, 'likes': 85 },
            { 'mid': 17686, 'name': 'Lie1092', 'sex': '男', 'img': '~@/assets/imgs/5.jpg', 'face': 'http://i1.hdslb.com/bfs/face/f175984309b7166595f3fe8f5347733272aae9dd.jpg', 'sign': '3天打渔2年撒网的UP主，任豚兼索狗', 'rank': 10000, 'level': 6, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '09-23', 'coins': 0, 'fans_badge': false, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 0, 'name': '', 'image': '', 'expire': 0, 'image_enhance': '' }, 'nameplate': { 'nid': 73, 'name': '人理拯救者', 'image': 'http://i2.hdslb.com/bfs/face/cce87ed0886232619f3c632b7735f4806ccd6fdd.png', 'image_small': 'http://i1.hdslb.com/bfs/face/a45c24d252668566114de87e40a73f4d90309d7b.png', 'level': '普通勋章', 'condition': 'FGO 1.0剧情完结纪念' }, 'is_followed': false, 'top_photo': 'http://i2.hdslb.com/bfs/space/2bf77a8e4397ec2ec10769b42db2f64895c08dbe.png', 'theme': {}, 'sys_notice': {}, 'following': 358, 'whisper': 0, 'black': 0, 'follower': 104, 'archive': { 'view': 11157 }, 'article': { 'view': 0 }, 'likes': 80 }
        ],

        topLikesUsers: [
            { 'mid': 27251, 'name': '花戶小鳩', 'sex': '男', 'face': 'http://i1.hdslb.com/bfs/face/8f13945afada2d5c2894ba5f9aa4ed224d5841e7.jpg', 'sign': 'cnm', 'rank': 10000, 'level': 5, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '11-16', 'coins': 0, 'fans_badge': false, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 252, 'name': '春原庄的管理人小姐', 'image': 'http://i2.hdslb.com/bfs/face/14738b92760b90675d4bf35dd059b0a666113bae.png', 'expire': 0, 'image_enhance': 'http://i2.hdslb.com/bfs/face/14738b92760b90675d4bf35dd059b0a666113bae.png' }, 'nameplate': { 'nid': 7, 'name': '见习搬运工', 'image': 'http://i2.hdslb.com/bfs/face/8478fb7c54026cd47f09daa493a1b1683113a90d.png', 'image_small': 'http://i2.hdslb.com/bfs/face/50eef47c3a30a75659d3cc298cfb09031d1a2ce5.png', 'level': '普通勋章', 'condition': '转载视频投稿通过总数>=10' }, 'is_followed': false, 'top_photo': 'http://i0.hdslb.com/bfs/space/b4cd9d75cfcb5bef7b10a4de6802f1b0246db736.png', 'theme': {}, 'sys_notice': {}, 'following': 114, 'whisper': 0, 'black': 0, 'follower': 346, 'archive': { 'view': 399625 }, 'article': { 'view': 0 }, 'likes': 1354 },
            { 'mid': 31142, 'name': 'Zuellni', 'sex': '保密', 'face': 'http://i2.hdslb.com/bfs/face/4464ff11501917abb3757b0f9e77acda1dcd070e.jpg', 'sign': '', 'rank': 10000, 'level': 6, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '', 'coins': 0, 'fans_badge': false, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 1, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '大会员', 'label_theme': 'vip' }, 'avatar_subscript': 1, 'nickname_color': '' }, 'pendant': { 'pid': 0, 'name': '', 'image': '', 'expire': 0, 'image_enhance': '' }, 'nameplate': { 'nid': 57, 'name': '收集萌新', 'image': 'http://i0.hdslb.com/bfs/face/7767275600ea63d351b22fa87ec15a79aa24e5e5.png', 'image_small': 'http://i0.hdslb.com/bfs/face/6589d992655595bf51543f268040eaeaed372fae.png', 'level': '普通勋章', 'condition': '同时拥有粉丝勋章>=5个' }, 'is_followed': false, 'top_photo': 'http://i2.hdslb.com/bfs/space/3ab888c1d149e864ab44802dea8c1443e940fa0d.png', 'theme': {}, 'sys_notice': {}, 'following': 63, 'whisper': 0, 'black': 0, 'follower': 56, 'archive': { 'view': 504283 }, 'article': { 'view': 0 }, 'likes': 233 },
            { 'mid': 257, 'name': '星界poi', 'sex': '保密', 'face': 'http://i1.hdslb.com/bfs/face/503535bac31f65db67c93140b0e9c24955a8bfb7.jpg', 'sign': 'ammp 忙成狗', 'rank': 10000, 'level': 5, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '', 'coins': 0, 'fans_badge': false, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 0, 'name': '', 'image': '', 'expire': 0, 'image_enhance': '' }, 'nameplate': { 'nid': 7, 'name': '见习搬运工', 'image': 'http://i1.hdslb.com/bfs/face/8478fb7c54026cd47f09daa493a1b1683113a90d.png', 'image_small': 'http://i1.hdslb.com/bfs/face/50eef47c3a30a75659d3cc298cfb09031d1a2ce5.png', 'level': '普通勋章', 'condition': '转载视频投稿通过总数>=10' }, 'is_followed': false, 'top_photo': 'http://i2.hdslb.com/bfs/space/cb1c3ef50e22b6096fde67febe863494caefebad.png', 'theme': {}, 'sys_notice': {}, 'following': 82, 'whisper': 0, 'black': 0, 'follower': 788, 'archive': { 'view': 2263490 }, 'article': { 'view': 0 }, 'likes': 131 },
            { 'mid': 32261, 'name': '龙de心', 'sex': '保密', 'face': 'http://i1.hdslb.com/bfs/face/5d2c92beb774a4bb30762538bb102d23670ae9c0.gif', 'sign': '', 'rank': 10000, 'level': 5, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '', 'coins': 0, 'fans_badge': false, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 0, 'name': '', 'image': '', 'expire': 0, 'image_enhance': '' }, 'nameplate': { 'nid': 0, 'name': '', 'image': '', 'image_small': '', 'level': '', 'condition': '' }, 'is_followed': false, 'top_photo': 'http://i0.hdslb.com/bfs/space/cb1c3ef50e22b6096fde67febe863494caefebad.png', 'theme': {}, 'sys_notice': {}, 'following': 15, 'whisper': 0, 'black': 0, 'follower': 39, 'archive': { 'view': 122431 }, 'article': { 'view': 0 }, 'likes': 124 },
            { 'mid': 553, 'name': '麻奥', 'sex': '保密', 'face': 'http://i1.hdslb.com/bfs/face/11d2cd814b17ef6738d910102a085a3418e508f1.jpg', 'sign': '没有飞天小裤裤和天麻还想要钱？！w(ﾟДﾟ)w', 'rank': 10000, 'level': 5, 'jointime': 0, 'moral': 0, 'silence': 0, 'birthday': '', 'coins': 0, 'fans_badge': true, 'official': { 'role': 0, 'title': '', 'desc': '', 'type': -1 }, 'vip': { 'type': 2, 'status': 1, 'theme_type': 0, 'label': { 'path': '', 'text': '年度大会员', 'label_theme': 'annual_vip' }, 'avatar_subscript': 1, 'nickname_color': '#FB7299' }, 'pendant': { 'pid': 217, 'name': 'citrus', 'image': 'http://i1.hdslb.com/bfs/face/f2d3a85b611eb2ef13cb64415187e3e9fd487ec8.png', 'expire': 0, 'image_enhance': 'http://i1.hdslb.com/bfs/face/f2d3a85b611eb2ef13cb64415187e3e9fd487ec8.png' }, 'nameplate': { 'nid': 40, 'name': '老司机', 'image': 'http://i1.hdslb.com/bfs/face/88013f24627e8db0ee3261adf7c8a7d0077c4d4e.png', 'image_small': 'http://i0.hdslb.com/bfs/face/075ed5043bdabcbe4f8bc6d730d630cb4b6ade13.png', 'level': '高级勋章', 'condition': '直播主播等级>=20级' }, 'is_followed': false, 'top_photo': 'http://i0.hdslb.com/bfs/space/44873d3568bdcb3d850d234e02a19602972450f1.png', 'theme': {}, 'sys_notice': {}, 'following': 106, 'whisper': 0, 'black': 0, 'follower': 1272, 'archive': { 'view': 3188 }, 'article': { 'view': 0 }, 'likes': 107 }
        ]
    }
  },
  mounted () {
    this.init_chart()
  },
  methods: {

    init_chart () {
        // 绘制图表。
            echarts.init(document.getElementById(1)).setOption(option1)
            echarts.init(document.getElementById(2)).setOption(option2)
            echarts.init(document.getElementById(3)).setOption(option3)
            echarts.init(document.getElementById(4)).setOption(option4)
            echarts.init(document.getElementById(5)).setOption(option5)
            // echarts.init(document.getElementById('column')).setOption(optionColumn)
    }
  }
}
</script>
