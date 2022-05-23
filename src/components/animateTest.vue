<template>
  <page-wrapper>
    <div class="pt-[20px]">
      <div class="flex p-[20px] bg-no-repeat overview">
        <div>
          <div
            v-for="(item, index) in tabs"
            :key="index"
            class="px-[20px] flex justify-between items-center
            w-[184px] h-[46px] text-[16px] rounded-lg cursor-pointer hover:text-primary
            transition duration-300 ease-out"
            :class="currentIndex === index ? 'bg-white text-primary' : ''"
            @click="handleClickToggle(index)"
          >
            {{ item.name }}
            <i
              v-if=" currentIndex === index"
              class="flex justify-center w-[24px] h-[24px] bg-[#e8f3ff] rounded-3xl"
            >
              <RightOutlined class="m-auto text-[12px]" />
            </i>
          </div>
        </div>
        <div class="my-[16px] ml-[39px] flex justify-between w-full">
          <div>
            <div class="text-[18px] text-[#1d2129] font-medium">
              {{ currentContent.title }}
            </div>
            <div class="mt-[12px] text-[14px]">
              {{ currentContent.desc }}
            </div>
            <a-button class="mt-[33px] text-[14px]" type="primary">
              {{ currentContent.btnText }}
            </a-button>
          </div>
          <div>
            <img :src="currentContent.imgUrl" class="mr-[48px]">
          </div>
        </div>
      </div>
    </div>
  </page-wrapper>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'


const tabs = [
  { id: 0, name: '渠道授权' },
  { id: 1, name: '商品上架' },
  { id: 2, name: '商品装修' },
  { id: 3, name: '支付配置' }
]

const contentList = [
  {
    title: '授权微信小程序、公众号',
    desc: '将您的微信公众号和小程序授权给我们，以便我们能为您提供搭建和上架小程序商城的能力',
    btnText: '去授权',
    imgUrl: '/src/assets/overview/channel.png'
  },
  {
    title: '在商城中上架商品',
    desc: '将您需要售卖的网校课程、班级、题库的商品信息添加到营销商城后台，编辑并上架后即可进行售卖',
    btnText: '去添加',
    imgUrl: '/src/assets/overview/commodity.png'
  },
  {
    title: '装修您的商城',
    desc: '可对商城页面进行灵活地自定义编辑，方便在商城中展示您的品牌、商品和营销活动',
    btnText: '去装修',
    imgUrl: '/src/assets/overview/furnish.png'
  },
  {
    title: '配置您的微信支付',
    desc: '检查或调整您的网校微信支付配置，实现商城交易流程',
    btnText: '去配置',
    imgUrl: '/src/assets/overview/pay-configure.png'
  }
]

const currentIndex = ref(0)

const handleClickToggle = (index: number) => {
  currentIndex.value = index
}

const currentContent = computed(() => {
  return contentList[currentIndex.value]
})
</script>

<style scoped>
.overview {
  background-image: url(../assets/overview/bg.png);
}
</style>
