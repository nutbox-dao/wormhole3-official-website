<template>
  <div>
    <div class="flex flex-col justify-center items-center section1 pt-6rem lg:pt-6rem pb-3rem max-w-1440px mx-auto">
      <img class="max-w-800px w-full xs:w-4/5 sm:w-7/10" src="~@/assets/home-img1.gif" alt="">
      <div class="-mt-6rem xs:-mt-6rem sm:-mt-10rem md:-mt-12rem lg:-mt-13rem whitespace-pre-line text-center px-6">
        <div class="text-34px leading-34px xs:text-34px sm:text-48px sm:leading-48px
                  md:text-60px md:leading-60px lg:text-78px lg:leading-78px
                  font-MonsterratMedium">{{$t('home.section1P1')}}</div>
        <div class="max-w-660px mx-auto mt-32px font-MonsterratLight opacity-50 leading-20px">
          {{$t('home.section1P2')}}
        </div>
        <div class="max-w-660px mx-auto mt-24px font-MonsterratLight opacity-50 leading-20px">
          {{$t('home.section1P3')}}
        </div>
      </div>
      <div class="mt-54px flex gap-24px">
        <button class="h-40px rounded-full px-20px bg-white text-black min-w-136px" @click="gotoWormhole">{{$t('home.getStart')}}</button>
        <button class="border-2 border-white rounded-full px-20px min-w-136px" @click="gotoDC">{{$t('home.join')}}</button>
      </div>
    </div>
    <div class="max-w-1080px px-15px sm:px-2rem mx-auto pt-4rem">
      <div class="section2">
        <div class="font-MonsterratMedium text-36px leading-38px md:text-60px md:leading-64px text-center">
          {{$t('home.feature')}}
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-x-30px mt-60px max-w-524px md:max-w-full mx-auto section2-content">
          <div class="col-span-1 mr-20px">
            <div class="">
              <div class="flex">
                <div class="border-t-1 border-primaryColor font-MonsterratBlack text-20px py-20px min-w-60px"
                     :class="carouselIndex===0?'text-primaryColor':'text-white'">01</div>
                <div class="border-t-1 border-white/50 ml-10px py-20px text-12px leading-18px xs:text-16px xs:leading-24px"
                     :class="carouselIndex===0?'text-primaryColor':'text-white'">
                  {{$t('home.section2P1')}}
                </div>
              </div>
              <div class="flex">
                <div class="border-t-1 border-primaryColor font-MonsterratBlack text-20px py-20px min-w-60px"
                     :class="carouselIndex===1?'text-primaryColor':'text-white'">02</div>
                <div class="border-t-1 border-white/50 ml-10px py-20px text-12px leading-18px xs:text-16px xs:leading-24px"
                     :class="carouselIndex===1?'text-primaryColor':'text-white'">
                  {{$t('home.section2P2')}}
                </div>
              </div>
              <div class="flex">
                <div class="border-t-1 border-primaryColor font-MonsterratBlack text-20px py-20px min-w-60px"
                     :class="carouselIndex===2?'text-primaryColor':'text-white'">03</div>
                <div class="border-t-1 border-white/50 ml-10px py-20px text-12px leading-18px xs:text-16px xs:leading-24px"
                     :class="carouselIndex===2?'text-primaryColor':'text-white'">
                  {{$t('home.section2P3')}}
                </div>
              </div>
            </div>
          </div>
          <div class="col-span-1">
            <el-carousel :height="carouselHeight" indicator-position="none"
                         :interval="3500" arrow="never" :autoplay="true"
                         :initial-index="carouselIndex"
                         ref="featureCarouselRef"
                         @change="carouselChange">
              <el-carousel-item>
                <img class="mx-auto w-full object-contain" src="~@/assets/feature-img1.png" alt="">
              </el-carousel-item>
              <el-carousel-item>
                <img class="mx-auto w-full object-contain" src="~@/assets/feature-img2.png" alt="">
              </el-carousel-item>
              <el-carousel-item>
                <img class="mx-auto w-full object-contain" src="~@/assets/feature-img3.png" alt="">
              </el-carousel-item>
            </el-carousel>
            <div class="flex items-center justify-center gap-x-20px py-20px">
              <button class="disabled:opacity-50"
                      :disabled="carouselIndex===0"
                      @click="setCarouselIndex(carouselIndex-1)">
                <img class="transform rotate-180 w-2.6rem h-2.6rem" src="~@/assets/icon-change-primary.svg" alt="">
              </button>
              <button class="disabled:opacity-50"
                      :disabled="carouselIndex===2"
                      @click="setCarouselIndex(carouselIndex+1)">
                <img class="w-2.6rem h-2.6rem" src="~@/assets/icon-change-primary.svg" alt="">
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="section3 mt-5rem pb-3rem md:pt-6rem">
        <div class="flex flex-col sm:flex-row max-w-524px sm:max-w-full mx-auto">
          <div class="flex-1 flex flex-col justify-center lg:min-w-520px">
            <div class="text-36px md:text-48px lg:text-56px lg:leading-68px font-MonsterratMedium">
              {{$t('home.section3P1')}}
            </div>
            <div class="text-12px leading-20px sm:text-16px sm:leading-24px mt-20px md:mt-32px">
              {{$t('home.section3P2')}}
            </div>
            <div class="">
              <button class="mt-20px" @click="gotoWormhole">
                <img class="h-36px md:h-2.6rem" src="~@/assets/icon-link-primary.svg" alt="">
              </button>
            </div>
          </div>
          <div class="flex-1 p-2rem xs:px-4rem sm:p-0 ml-1rem">
            <img class="w-full" src="~@/assets/home-img2.png" alt="">
          </div>
        </div>
      </div>
      <div class="section4 md:pt-6rem">
        <div class="flex flex-col flex-col-reverse sm:flex-row max-w-524px sm:max-w-full mx-auto">
          <div class="flex-1 p-2rem xs:px-4rem sm:pl-0 sm:pr-5rem">
            <img class="w-full" src="~@/assets/home-img3.png" alt="">
          </div>
          <div class="flex-1 flex flex-col justify-center">
            <div class="text-36px md:text-48px lg:text-56px lg:leading-68px font-MonsterratMedium">
              {{$t('home.section4P1')}}
            </div>
            <div class="text-12px leading-20px sm:text-16px sm:leading-24px mt-20px md:mt-32px">
              {{$t('home.section4P2')}}
            </div>
            <div class="text-right">
              <button class="mt-20px" @click="gotoWormhole">
                <img class="h-36px md:h-2.6rem" src="~@/assets/icon-link-primary.svg" alt="">
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="section5 py-3rem">
        <div class="flex flex-col sm:flex-row max-w-524px sm:max-w-full mx-auto">
          <div class="flex-1 flex flex-col justify-center md:mt-1/5">
            <div class="text-36px md:text-48px lg:text-56px lg:leading-68px font-MonsterratMedium">
              {{$t('home.section5P1')}}
            </div>
            <div class="text-12px leading-20px sm:text-16px sm:leading-24px mt-20px md:mt-32px">
              {{$t('home.section5P2')}}
            </div>
            <div class="">
              <button class="mt-20px" @click="gotoWormhole">
                <img class="h-36px md:h-2.6rem" src="~@/assets/icon-link-primary.svg" alt="">
              </button>
            </div>
          </div>
          <div class="flex-1 px-2rem xs:px-4rem sm:p-0">
            <img class="w-full" src="~@/assets/home-img4.png" alt="">
          </div>
        </div>
      </div>
      <div class="section6 mt-4rem md:pt-6rem overflow-hidden">
        <div class="font-MonsterratMedium text-36px leading-38px md:text-60px md:leading-64px text-center">
          {{$t('roadmap.roadmap')}}
        </div>
        <div class="w-full overflow-x-auto overflow-y-hidden no-scroll-bar mt-2rem md:mt-8rem">
          <div class="w-max roadmap-container">
            <div class="flex items-end mt-10px">
              <div class="w-180px min-w-180px max-w-180px pl-10px border-l-1 border-white/30 relative mr-100px ml-5px roadmap-item">
                <span class="absolute -left-4px top-0 w-8px min-w-8px h-8px min-h-8px rounded-full bg-colorE3 circle"></span>
                <div class="font-MonsterratBlack text-20px leading-24px mb-24px time">{{$t('roadmap.t1')}}</div>
                <div class="font-MonsterratMedium text-16px leading-16px mb-8px">{{$t('roadmap.h1')}}</div>
                <div class="text-12px leaing-16px opacity-50">{{$t('roadmap.p1')}}</div>
              </div>
              <div class="w-180px min-w-180px max-w-180px pl-10px border-l-1 border-white/30 relative mr-100px roadmap-item">
                <span class="absolute -left-4px top-0 w-8px min-w-8px h-8px min-h-8px rounded-full bg-colorE3 circle"></span>
                <div class="font-MonsterratBlack text-20px leading-24px mb-24px time">{{$t('roadmap.t3')}}</div>
                <div class="font-MonsterratMedium text-16px leading-16px mb-8px">{{$t('roadmap.h3')}}</div>
                <div class="text-12px leaing-16px opacity-50">{{$t('roadmap.p3')}}</div>
              </div>
              <div class="w-180px min-w-180px max-w-180px pl-10px border-l-1 border-white/30 relative mr-100px roadmap-item">
                <span class="absolute -left-4px top-0 w-8px min-w-8px h-8px min-h-8px rounded-full bg-colorE3 circle"></span>
                <div class="font-MonsterratBlack text-20px leading-24px mb-24px time">{{$t('roadmap.t5')}}</div>
                <div class="font-MonsterratMedium text-16px leading-16px mb-8px">{{$t('roadmap.h5')}}</div>
                <div class="text-12px leaing-16px opacity-50">{{$t('roadmap.p5')}}</div>
              </div>
              <div class="w-180px min-w-180px max-w-180px pl-10px border-l-1 border-white/30 relative roadmap-item">
                <span class="absolute -left-4px top-0 w-8px min-w-8px h-8px min-h-8px rounded-full bg-colorE3 circle"></span>
                <div class="font-MonsterratBlack text-20px leading-24px mb-24px time">{{$t('roadmap.t7')}}</div>
                <div class="font-MonsterratMedium text-16px leading-16px mb-8px">{{$t('roadmap.h7')}}</div>
                <div class="text-12px leaing-16px opacity-50">{{$t('roadmap.p7')}}</div>
              </div>
            </div>
            <div class="w-full h-1px bg-color97 my-15px"></div>
            <div class="flex items-start">
              <div class="w-180px min-w-180px max-w-180px pl-10px border-l-1 border-white/30 relative mr-100px ml-200px roadmap-item">
                <span class="absolute -left-4px top-0 w-8px min-w-8px h-8px min-h-8px rounded-full bg-colorE3 circle"></span>
                <div class="font-MonsterratBlack text-20px leading-24px mb-24px time">{{$t('roadmap.t2')}}</div>
                <div class="font-MonsterratMedium text-16px leading-16px mb-8px">{{$t('roadmap.h2')}}</div>
                <div class="text-12px leaing-16px opacity-50">{{$t('roadmap.p2')}}</div>
              </div>
              <div class="w-180px min-w-180px max-w-180px pl-10px border-l-1 border-white/30 relative mr-100px roadmap-item">
                <span class="absolute -left-4px top-0 w-8px min-w-8px h-8px min-h-8px rounded-full bg-colorE3 circle"></span>
                <div class="font-MonsterratBlack text-20px leading-24px mb-24px time">{{$t('roadmap.t4')}}</div>
                <div class="font-MonsterratMedium text-16px leading-16px mb-8px">{{$t('roadmap.h4')}}</div>
                <div class="text-12px leaing-16px opacity-50">{{$t('roadmap.p4')}}</div>
              </div>
              <div class="w-180px min-w-180px max-w-180px pl-10px border-l-1 border-white/30 relative mr-100px roadmap-item">
                <span class="absolute -left-4px top-0 w-8px min-w-8px h-8px min-h-8px rounded-full bg-colorE3 circle"></span>
                <div class="font-MonsterratBlack text-20px leading-24px mb-24px time">{{$t('roadmap.t4')}}</div>
                <div class="font-MonsterratMedium text-16px leading-16px mb-8px">{{$t('roadmap.h4')}}</div>
                <div class="text-12px leaing-16px opacity-50">{{$t('roadmap.p4')}}</div>
              </div>
            </div>
          </div>

        </div>
      </div>
      <div class="section7 mt-4rem py-3rem">
        <div class="flex gap-x-30px flex-col sm:flex-row mx-auto">
          <div class="flex-1 flex flex-col justify-center items-center sm:items-start">
            <div class="text-36px md:text-48px lg:text-56px lg:leading-68px font-MonsterratMedium">
              {{$t('partner.partner')}}
            </div>
          </div>
          <div class="flex-1 grid grid-cols-2 justify-center items-center gap-x-20px">
            <div class="col-span-1">
              <img class="max-h-120px" src="~@/assets/partner-logo0.png" alt="">
            </div>
            <div class="col-span-1">
              <img class="max-h-120px" src="~@/assets/partner-logo1.png" alt="">
            </div>
            <div class="col-span-1">
              <img class="max-h-120px" src="~@/assets/partner-logo2.png" alt="">
            </div>
            <div class="col-span-1">
              <img class="max-h-120px" src="~@/assets/partner-logo3.png" alt="">
            </div>
            <div class="col-span-1">
              <img class="max-h-120px" src="~@/assets/partner-logo4.png" alt="">
            </div>
            <div class="col-span-1">
              <img class="max-h-120px" src="~@/assets/partner-logo5.png" alt="">
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {onMounted, onUnmounted, ref} from "vue";

const carouselIndex = ref(0)
const featureCarouselRef = ref()
const carouselChange = (index) => {
  carouselIndex.value = index
}
const setCarouselIndex = (index) => {
  carouselIndex.value = index
  featureCarouselRef.value.setActiveItem(index)
}
const carouselHeight = ref('500px')
const gotoWormhole = () => {
  window.open('https://alpha.wormhole3.io', '__blank')
}
const gotoDC = () => {
  window.open('https://discord.gg/6QbcvSEDWF', '__blank')
}
onMounted(() => {
  const screenWidth = document.body.offsetWidth
  if(screenWidth<524) carouselHeight.value = screenWidth - 40 + 'px'
  if(screenWidth>960 && screenWidth <1080) carouselHeight.value = '450px'
  window.addEventListener('resize', () => {
    const screenWidth = document.body.offsetWidth
    if(screenWidth<524) carouselHeight.value = screenWidth - 40 + 'px'
    if(screenWidth>960 && screenWidth <1080) carouselHeight.value = '450px'
  });
})
onUnmounted(() => {
  window.removeEventListener('resize',() => {})
})
</script>

<style scoped>
.section1 {
  background-image: url("~@/assets/home-bg1.png"), url("~@/assets/home-bg2.png");
  background-repeat: no-repeat;
  background-position: left top, right bottom;
  background-size: 70%, 60%;
}
@media (max-width: 500px) {
  .section1 {
    background-size: 100%, 80%;
    background-position: left top, right 60%;
  }
}
@media (min-width: 1080px) {
  .section1 {
    /*background-size: 70%, 60%;*/
    background-position: 20% top, right 120%;
  }
}
.section2-content {
  background-image: url("~@/assets/feature-bg1.svg");
  background-repeat: no-repeat;
  background-position: center bottom;
  background-size: 100% auto;
}
.roadmap-container {
  animation: move-scroll 12s linear infinite;
}
.roadmap-container:hover {
  animation-play-state: paused;
}
.roadmap-item {
  cursor: pointer;
}
.roadmap-item:hover {
  transform: translateY(-5px);
}
.roadmap-item:hover .circle {
  background: #8534F2;
}
.roadmap-item:hover .time {
  color: #8534F2;
}
@keyframes move-scroll {
  0%
  {
    opacity:0;
  }
  1%
  {
    opacity:1;
    transform:translateX(20%);
  }
  90%
  {
    opacity:1;
    transform:translateX(-60%);
  }
  98%
  {
    opacity: 0;
    transform:translateX(-65%);
  }
  100%
  {
    opacity:0;
    left: 0;
  }
}
</style>
