<template>
  <div class=''>
    {{x}}
    <view>
      <text>uni-card</text>
      <uni-card />
    </view>
    <view>
      <text>xe-button</text>
    </view>
  </div>
</template>

<script lang='ts'>
import { ref, Ref, onMounted, defineComponent } from 'vue';
// import XeButton from '@ltestrepo/components/lib/xe-button/xe-button.vue'
export default defineComponent({
  name: 'XeButton',
  setup() {
    const x: Ref<string> = ref('button');
    return {
      x
    }
  }
})
</script>
<style lang='scss' scoped>
</style>
