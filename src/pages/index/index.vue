<template>
  <view class="index">
    <!-- 距离下班时间 -->
    <RemainTime />
    <!-- 展示上班金额 -->
    <Counter />
    <!-- 距离时间组合 -->
    <TimeCom />
  </view>
</template>

<script>
import './index.less'
import Counter from '../../components/Counter.vue'
import RemainTime from '../../components/RemainTime.vue'
import TimeCom from '../../components/TimeCom.vue'

export default {
  name: 'Index',
  components: {
    Counter,
    RemainTime,
    TimeCom
  }
}
</script>
