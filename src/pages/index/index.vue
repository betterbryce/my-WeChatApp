<template>
  <view class="index">
    <!-- 距离下班时间 -->
    <Todo />
    <!-- 展示上班金额 -->
    <Counter />
  </view>
</template>

<script>
import './index.less'
import Counter from '../../components/Counter.vue'
import Todo from '../../components/Todo.vue'

export default {
  name: 'Index',
  components: {
    Counter,
    Todo
  }
}
</script>
