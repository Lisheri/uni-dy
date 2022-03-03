<template>
  <view class=''>
    {{ title }}
    <view class="fuck">
      <slot :title="titleGo" />
    </view>
    <view>{{ props.foo }}</view>
    <view>{{ props.bar }}</view>
  </view>
</template>

<script setup lang='ts'>
import { ref, Ref, onMounted } from 'vue';
import { IPropsTypes } from './types';

const props = defineProps<{
  foo: string | number;
  bar?: string;
}>();

const emit = defineEmits<{
  (e: 'change', id?: number | string): void;
  (e: 'fuck', text?: string): void;
}>();

const title = ref('good')
const titleGo = ref('fuck')
// 需传入生命周期执行函数
onMounted(() => {
  emit('change', titleGo.value);
})
</script>
<style lang='scss' scoped>
</style>
