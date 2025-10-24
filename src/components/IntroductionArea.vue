<template>
<section class="Introduction-area" @mouseenter="handleMouseEnter" @mouseleave="handleMouseLeave">
  <div class="swiper-container">
    
    <!-- 轮播控制按钮 -->
    <div class="swiper-control-pre">
      <button tabindex="0" class="control-btn control-btn-left" 
              @click="prevSlide"
              @mouseenter="hoverPrev = true"
              @mouseleave="hoverPrev = false">
        <span class="control-arrow-left">
          <div class="arrow-icon"></div>
        </span>
      </button>
    </div>
    
    <div class="swiper-control-next">
      <button tabindex="0" class="control-btn control-btn-right"
              @click="nextSlide"
              @mouseenter="hoverNext = true"
              @mouseleave="hoverNext = false">
        <span class="control-arrow-right">
          <div class="arrow-icon"></div>
        </span>
      </button>
    </div>
    
    <!-- 轮播内容 -->
    <div id="swiper-wrapper" class="swiper-wrapper">
      
      <!-- 总展示 轮播项 -->
      <div class="swiper-slide" 
           :class="{ 'active': currentSlide === 0 }"
           v-show="currentSlide === 0">
        <a href="#" class="banner-link" tabindex="-1"></a>
        <div class="banner-content theme1">
          <div class="banner-text">
            <div class="top-content">
              <div class="eyebrow-text eyebrow">1</div>
            </div>
            <img alt="图1" class="banner-logo banner-headline" src="#">
          </div>
          <div class="banner-btn-box">
            <a href="#" class="banner-button" tabindex="-1">
              <div class="text">了解更多</div>
              <div class="button-icon"></div>
            </a>
          </div>
        </div>
      </div>
      
      <!-- 应急物流 轮播项 -->
      <div class="swiper-slide" 
           :class="{ 'active': currentSlide === 1 }"
           v-show="currentSlide === 1">
        <a href="#" class="banner-link" tabindex="-1"></a>
        <div class="banner-content theme2">
          <div class="banner-text">
            <div class="top-content">
              <div class="eyebrow-text eyebrow">2</div>
            </div>
            <img alt="图2" class="banner-logo banner-headline" src="#">
          </div>
          <div class="banner-btn-box">
            <a href="#" class="banner-button" tabindex="-1">
              <div class="text">了解更多</div>
              <div class="button-icon"></div>
            </a>
          </div>
        </div>
      </div>
      
    </div>
    
    <!-- 轮播指示器 -->
    <div class="swiper-scroller">
      <div v-for="(slide, index) in slides" 
           :key="index" 
           class="slider" 
           :class="{ 'active': currentSlide === index }"
           @click="goToSlide(index)">
        <div class="progress" :style="{ width: currentSlide === index ? progressWidth + '%' : '0%' }"></div>
      </div>
      
      <ul class="swiper-scroller-list">
        <li v-for="(slide, index) in slides" 
            :key="index" 
            class="swiper-scroller-item"
            :class="{ 'active': currentSlide === index }"
            @click="goToSlide(index)">
          <a href="javascript:;" tabindex="-1">{{ slide.title }}</a>
        </li>
      </ul>
    </div>
  </div>
</section>
</template>

<script>
export default {
  name: 'IntroductionArea',
  data() {
    return {
      currentSlide: 0,
      hoverPrev: false,
      hoverNext: false,
      isHovering: false,
      autoPlayTimer: null,
      progressWidth: 0,
      progressInterval: null,
      slides: [
        {
          title: 'DJI FlyCart 100',
          eyebrow: '全能智运旗舰',
          slogan: '运载无界'
        },
        {
          title: 'Osmo Mobile 8',
          eyebrow: '全场景精准跟拍手机稳定器',
          slogan: '自由开拍，跟随精彩'
        }
      ]
    }
  },
  methods: {
    nextSlide() {
      this.currentSlide = (this.currentSlide + 1) % this.slides.length;
      this.resetAutoPlay();
    },
    prevSlide() {
      this.currentSlide = (this.currentSlide - 1 + this.slides.length) % this.slides.length;
      this.resetAutoPlay();
    },
    goToSlide(index) {
      this.currentSlide = index;
      this.resetAutoPlay();
    },
    handleMouseEnter() {
      this.isHovering = true;
    },
    handleMouseLeave() {
      this.isHovering = false;
    },
    startAutoPlay() {
      // 清除现有定时器
      if (this.autoPlayTimer) {
        clearInterval(this.autoPlayTimer);
      }
      if (this.progressInterval) {
        clearInterval(this.progressInterval);
      }
      
      // 重置进度条
      this.progressWidth = 0;
      
      // 进度条动画
      this.progressInterval = setInterval(() => {
        this.progressWidth += (100 / 100); // 10秒完成100%
      }, 100);
      
      // 自动轮播
      this.autoPlayTimer = setInterval(() => {
        if (!this.isHovering) { // 只有不在悬停状态时才自动播放
          this.nextSlide();
        }
      }, 10000);
    },
    resetAutoPlay() {
      this.progressWidth = 0;
      this.startAutoPlay();
    }
  },
  mounted() {
    this.startAutoPlay();
  },
  beforeUnmount() {
    if (this.autoPlayTimer) {
      clearInterval(this.autoPlayTimer);
    }
    if (this.progressInterval) {
      clearInterval(this.progressInterval);
    }
  }
}
</script>

<style scoped>
.Introduction-area {
    box-sizing: inherit;
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font-weight: 400;
    background: 0 0;
    display: block;
    position: relative;
    width: 100%;
    background-color: #ededed;
    z-index: 800;
    height: 640px;
    overflow: hidden;
}

.swiper-container {
    position: relative;
    width: 100%;
    height: 100%;
}

.swiper-wrapper {
    position: relative;
    width: 100%;
    height: 100%;
}

.swiper-slide {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    transition: opacity 0.5s ease;
    opacity: 0;
}

.swiper-slide.active {
    opacity: 1;
}

/* 轮播控制按钮样式 */
.swiper-control-pre,
.swiper-control-next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    z-index: 10;
}

.swiper-control-pre {
    left: 20px;
}

.swiper-control-next {
    right: 20px;
}

.control-btn {
    width: 48px;
    height: 48px;
    border: none;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s ease;
    opacity: 0;
}

.Introduction-area:hover .control-btn {
    opacity: 1;
    background: rgba(255, 255, 255, 0.8);
}

.control-btn:hover {
    background: rgba(0, 0, 0, 0.8) !important;
    transform: scale(1.1);
}

.arrow-icon {
    width: 16px;
    height: 16px;
    border: solid #333;
    border-width: 0 2px 2px 0;
    display: inline-block;
    transition: all 0.3s ease;
}

.control-btn-left .arrow-icon {
    transform: rotate(135deg);
}

.control-btn-right .arrow-icon {
    transform: rotate(-45deg);
}

.control-btn:hover .arrow-icon {
    border-color: white;
}

/* 轮播指示器样式 */
.swiper-scroller {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 8px;
    z-index: 10;
}

.slider {
    width: 40px;
    height: 4px;
    background: rgba(255, 255, 255, 0.5);
    border-radius: 2px;
    cursor: pointer;
    overflow: hidden;
    position: relative;
}

.slider.active {
    background: rgba(255, 255, 255, 0.3);
}

.progress {
    height: 100%;
    background: white;
    border-radius: 2px;
    transition: width 0.1s linear;
}

.swiper-scroller-list {
    display: none;
}

/* 轮播内容样式 */
.banner-content {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 0 20px;
    background-color: antiquewhite;
}

.banner-logo {
    width: 50px;
    height: 20px;
    margin-bottom: 20px;
    background-color: aquamarine;
}

.banner-text {
    margin-bottom: 30px;
}

.banner-btn-box {
    display: flex;
    gap: 15px;
}

.banner-button {
    display: flex;
    align-items: center;
    padding: 10px 20px;
    background: rgba(0, 0, 0, 0.2);
    border: 1px solid rgba(255, 255, 255, 0.5);
    border-color: rgba(0, 0, 0, 0.5);
    border-radius: 4px;
    color: #333;
    text-decoration: none;
    transition: all 0.3s ease;
}

.banner-button:hover {
    background: rgba(0, 0, 0, 0.3);
}

.theme1 {
    background-color: #a3d2ca;
}
.theme2 {
    background-color: #f7d6bf;
}
</style>