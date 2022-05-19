<template>
  <div>
    <div @click="qjt">
      <van-nav-bar title="请假详情" left-arrow fixed />
    </div>
    <div class="subject">
      <img id="img" src="../assets/img.png" alt="" />
      <div class="div0"></div>
      <div class="div1">
        <van-row>
          <van-col span="4"
            ><div class="div333"></div>
            <div class="div111">{{ name1 }}</div></van-col
          >

          <van-col span="14" id="name">
            <span>{{ username }}</span>
            <span class="t1">销假审批中</span>
          </van-col>
          <van-col span="6"><img src="../assets/提醒.png" class="name_img" alt="" /></van-col>
        </van-row>
        <van-cell-group>
          <van-cell title="所在班级" :value="bj" :border="false" />
          <van-cell title="请假类型" value="事假" :border="false" />
          <van-cell title="开始时间" :value="start_time" :border="false" />
          <van-cell title="结束时间" :value="End_time" :border="false" />
          <van-cell title="请假天数" value="0.5天" :border="false" />
          <van-cell title="是否离校" value="离校" :border="false" />
          <van-cell title="请假事由" value="外出" :border="false" />
        </van-cell-group>
      </div>
      <div class="div0"></div>
      <div class="div2">
        <van-cell-group>
          <van-cell title="紧急联系人名称" :value="lxr" :border="false" />
          <van-cell title="紧急联系人电话" :value="lxrhm" :border="false" />
        </van-cell-group>
      </div>
      <div class="div0"></div>
      <div class="div3">
        <van-cell-group>
          <van-cell title="请假时所在位置" label="湖南省衡阳市珠晖区苗圃街道中共衡阳财经工业职业技术学院委员会湖南财经工业职业技术学院" :border="false" />
        </van-cell-group>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Qin',
  props: ['username', 'bj', 'lxr', 'lxrhm', 'calendar'],
  created() {
    this.init(), (this.name1 = this.username.slice(1))
  },
  data() {
    return {
      start_time: '',
      End_time: '',
      name1: ''
    }
  },
  methods: {
    qjt() {
      this.$emit('tz')
      // console.log('a')
    },
    init() {
      ;(this.start_time = '2022-' + this.calendar + ' 9:00'), (this.End_time = '2022-' + this.calendar + ' 21:00')
      // var q = this.calendar
      // console.log(this.start_time)
    }
  }
}
</script>

<style lang="less" scoped>
#img {
  width: 100%;
  padding: 12vw 0 0 0;
}
.van-col {
  height: 15vw;
}
.van-row {
  border-bottom: 1px solid #e7e7e7;
}
.van-cell__value {
  flex: 4;
  text-align: left;
}
#name {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.t1 {
  color: #e3b579;
  font-size: 2vw;
}
.name_img {
  width: 100%;
}
.div0 {
  background-color: #f8f8f8;
  height: 3vw;
}

.div111 {
  background-color: #51adff;
  width: 12vw;
  height: 12vw;
  margin: 0 auto;
  border-radius: 50%;
  text-align: center;
  line-height: 12vw;
  font-size: 4vw;
  color: #fff;
}
.div333 {
  // background-color: pink;
  height: 2vw;
}
</style>
