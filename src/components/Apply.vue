<template>
  <div>
    <van-form @submit="onSubmit">
      <van-field v-model="username" name="username" label="用户名" placeholder="姓名" />
      <van-field v-model="bj" name="bj" label="班级" placeholder="写班级全称(计算机应用技术20计应1班)" />
      <van-field v-model="lxr" name="lxr" label="紧急联系人" placeholder="紧急联系人" />
      <van-field v-model="lxrhm" name="lxrhm" label="紧急联系号码" placeholder="中间四位写成*(111****1111)" />
      <van-field readonly clickable name="calendar" :value="dataValue" label="日期" placeholder="点击选择开始日期" @click="showCalendar = true" />
      <van-calendar v-model="showCalendar" @confirm="onConfirm1" />
      <div style="margin: 16px">
        <van-button round block type="info" native-type="submit">提交</van-button>
      </div>
    </van-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      bj: '',
      lxr: '',
      lxrhm: '',
      dataValue: '',
      showPicker: false,
      showCalendar: false
    }
  },
  methods: {
    onSubmit(values) {
      // console.log('submit', values)
      this.$emit('assignment', values)
    },
    onConfirm1(date) {
      this.dataValue = `${date.getMonth() + 1}-${date.getDate()}`
      this.showCalendar = false
    }
  }
}
</script>

<style></style>
