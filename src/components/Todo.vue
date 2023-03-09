<template>
	<text>当前剩余时间为:{{nowTime}}</text>
</template>
<script>
import { ref, onMounted, onBeforeUnmount } from 'vue'

export default {
	setup() { 
    let timer = ref({})
    var nowTime = ref('')

    //计算距离下班时间
    const dateFormat = () => {
      var date = new Date()
      var hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours()
      var minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes()
      var seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds()
      return ((18 - hours - 1) + ":" + (60 - minutes - 1) + ":" + (60 - seconds))
    }

	  //在挂载时启动定时器
    onMounted(() => {
      console.log('DOM挂载完毕')
      timer = setInterval(() => {
        nowTime.value = dateFormat()
      }, 1000)
    })

    //实例销毁之前清除定时器
    onBeforeUnmount(() => {
      console.log('即将销毁')
      if (timer) {
        clearInterval(timer)
      }
    })
    return{
			nowTime
		}
  }
}
</script>
