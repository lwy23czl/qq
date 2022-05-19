<template>
  <div class="head">
    <van-nav-bar title="请假" left-arrow fixed />
    <img id="img" src="../assets/img.png" alt="" />
    <div class="choice">
      <img src="../assets/选择.png" alt="" />
    </div>
    <div class="div0"></div>
    <van-row @click="qjt">
      <van-col span="4">
        <!-- <img src="../assets/name.png" alt="" class="name_img" /> -->
        <div class="div333"></div>
        <div class="div111">{{ name1 }}</div>
      </van-col>
      <van-col span="18" class="name">
        <span class="big">已提交请假</span>
        <span>请假类型:事假</span>
        <span>请假时间: {{ start_time }}</span>
        <span>结束时间: {{ End_time }}</span>
        <span class="t1">待销假</span>
      </van-col>
      <van-col span="2" class="time">10:00</van-col>
    </van-row>
    <div class="div3"></div>
    <div class="last">
      <van-button class="button" type="info" size="large">我要请假</van-button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['username', 'bj', 'lxr', 'lxrhm', 'calendar'],
  created() {
    this.init(), (this.name1 = this.username.slice(1))
  },
  data() {
    return {
      start_time: '',
      End_time: ''
    }
  },
  methods: {
    qjt() {
      this.$emit('tz')
      // console.log('a')
    },
    init() {
      ;(this.start_time = '2022-' + this.calendar + ' 9:00'), (this.End_time = '2022-' + this.calendar + ' 21:00')
    }
  }
}
</script>

<style lang="less" scoped>
.t1 {
  color: #e3b579;
}
#img {
  width: 100%;
  padding: 12vw 0 0 0;
}
.choice img {
  width: 100%;
}
.div0 {
  background-color: #f8f8f8;
  height: 3vw;
}
.name {
  display: flex;
  flex-direction: column;
  justify-content: center;
  font-size: 2vw;
  color: #bbbbbb;
}
.name_img {
  width: 100%;
}
.time {
  font-size: 2vw;
  color: #bbbbbb;
}
.big {
  font-size: 4vw;
  font-weight: 700;
  color: black;
}
.last {
  height: 15vw;
  width: 100%;
  background-color: #fff;
  position: fixed;
  bottom: 0;
  display: flex;
  justify-content: center;
}
.div3 {
  background-color: #f8f8f8;
  height: 80vw;
}
.button {
  border-radius: 20px;
}
.div111 {
  background-color: #51adff;
  width: 15vw;
  height: 15vw;
  margin: 0 auto;
  border-radius: 50%;
  text-align: center;
  line-height: 15vw;
  font-size: 5vw;
  color: #fff;
}
.div333 {
  // background-color: pink;
  height: 3vw;
}
</style>
