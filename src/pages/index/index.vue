<template>
  <view class="content">
    <image class="logo" src="/static/logo.png" />
    <view class="text-area">
      <text class="title">{{ title }}</text>
      <view>
        <button @click="handleChangeTitle" :class="[title]">点击变化类</button>
      </view>
      <view
        :style="{
          width: type === 0 ? '100px' : '200px'
        }"
      >
        <button @click="handleCountAdd">点击改变count</button>
      </view>
      <text>{{ count }}</text>
    </view>
    <page-container1
      foo="123"
      bar="卧槽"
      @change="handlePageChange"
    >
      <template v-slot="{title}">
        {{ title }}
      </template>
    </page-container1>
    <btn />
  </view>
</template>

<script setup lang="ts">
import { ref, Ref } from 'vue'
import PageContainer1 from '@/components/page-container/index.vue';
import btn from '@components/button/index.vue'
import XeButton from '@ltestrepo/components/lib/xe-button/xe-button.vue';
const title = ref('Hello')
const count: Ref<number> = ref(0)
const type = ref(0)

const handleChangeType = () => {
  type.value = 1
}

const handleChangeTitle = () => {
  title.value = 'change-hello'
}
const handleCountAdd = () => {
  count.value++
  handleChangeType()
}

const handlePageChange = (id?: number | string) => {
  console.info(id, '卧槽')
}
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}

.text-area {
  display: flex;
  justify-content: center;
  flex-direction: column;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
