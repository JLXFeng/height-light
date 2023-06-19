<script setup lang="ts">
import {onMounted} from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'


gsap.registerPlugin(ScrollTrigger);


onMounted(()=>{
 gsap.utils.toArray(".content").forEach((e,index)=>{
    ScrollTrigger.create({
      trigger: e as string,
      start: `center ${50 - index}%`,
      end: `bottom ${50 - index}%`,
      // markers:true,
      toggleClass: { className: 'active', targets: e as string },
    });
 })
})


</script>

<template>
  <div class="scrollbar-wrap"></div>
  <div class="content-wrap">
      <span class="content">这个常伴你左右的好伙伴, 超有能耐。</span>
      <span class="content">体温感应功能,帮女性洞察自身的健康;</span>
      <span class="content">车祸检测待命,紧急时刻主动呼叫救援;</span>
      <span class="content">睡眠阶段跟测, 让你更了解自己的睡眠状况;</span>
      <span class="content">还有进阶的体能训练 app，为锻炼加分。</span>
      <span class="content">就让一个更健康的未来，更漂亮地开始吧。</span>
  </div>
   <div class="scrollbar-wrap"></div>
</template>

<style scoped>
  .scrollbar-wrap {
      height: 100vh;
    }
  .content-wrap{
    max-width: 1000px;
    margin: 0 auto;
  }
  .content {
      opacity: .45;
      color: #fff;
      font-size: 64px;
      font-weight: 600;
      transition: opacity 200ms ease-in;
    }
     .content.active {
      opacity: 1;
    }
</style>
