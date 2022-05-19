<template>
  <div>
    <!-- <router-view></router-view> -->
    <!-- <home-page></home-page> -->
    <component :is="comName" @tz="go" @assignment="assignment" :username="username" :bj="bj" :lxr="lxr" :lxrhm="lxrhm" :calendar="calendar"></component>
  </div>
</template>

<script>
import HomePage from '@/components/HomePage.vue'
import Qin from '@/components/qingjiatiao.vue'
import Apply from '@/components/Apply.vue'
export default {
  components: { HomePage, Qin, Apply },
  data() {
    return {
      comName: 'Apply',
      username: '',
      bj: '',
      lxr: '',
      lxrhm: '',
      calendar: ''
    }
  },
  methods: {
    go() {
      this.comName == 'Qin' ? (this.comName = 'HomePage') : (this.comName = 'Qin')
    },
    assignment(value) {
      ;(this.comName = 'HomePage'), (this.username = value.username), (this.bj = value.bj), (this.lxr = value.lxr), (this.lxrhm = value.lxrhm), (this.calendar = value.calendar), console.log(this.username, this.bj, this.lxr, this.lxrhm, this.calendar)
    }
  }
}
</script>

<style></style>
