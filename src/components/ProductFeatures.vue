<template>
  <section class="product-features">
    <div class="features-container">
      <!-- 左侧产品图片 -->
      <div class="product-image-section">
        <div class="product-image">
          <!-- 产品图片区域，可以用纯色背景代替 -->
          <div class="image-placeholder">产品图片</div>
        </div>
      </div>
      
      <!-- 右侧特性区域 -->
      <div class="features-section">
        <h2 class="section-title">产 品 功 能</h2>
          <div class="title-description">
            <span class="description-line">高仿真度路径规划模型，高效率集成优化算法</span>
            <span class="description-line">全链路智慧物联系统及AICG赋能</span>
            <span class="description-line">交互体验</span>
          </div>
        <div class="features-grid">
          <div 
            v-for="(feature, index) in features" 
            :key="feature.id" 
            class="feature-card"
            :style="{ transform: `translateY(-${index * 15}px)` }"
            @mouseenter="hoverIndex = index"
            @mouseleave="hoverIndex = -1"
          >
            <div class="feature-content">
              <div class="feature-value">{{ feature.value }}</div>
              <div class="feature-label">{{ feature.label }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProductFeatures',
  data() {
    return {
      hoverIndex: -1,
      features: [
        { id: 1, value: '30min达', label: '快速响应' },
        { id: 2, value: '1080P', label: '高清摄像' },
        { id: 3, value: '99.99%', label: '可靠性' },
        { id: 4, value: '100Hz', label: '传输速度' }
      ]
    }
  }
}
</script>

<style scoped>
.product-features {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  margin: 0;
  padding: 80px 0;
  color: white;
  position: relative;
  overflow: hidden;
}

.features-container {
  max-width: 1500px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
  padding: 0 20px;
}

/* 左侧样式 */
.product-image-section {
  display: flex;
  justify-content: center;
  align-items: center;
}

.product-image {
  width: 100%;
  max-width: 400px;
  height: 300px;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
}

.image-placeholder {
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, rgba(255,255,255,0.1), rgba(255,255,255,0.2));
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  color: rgba(255, 255, 255, 0.8);
  border: 2px dashed rgba(255, 255, 255, 0.3);
}

/* 右侧样式 */
.features-section {
  position: relative;
}

.section-title {
  font-size: 46px;
  font-weight: 700;
  margin-bottom: 20px;
  margin-right: 30px;
  text-align: right;
  color: white;
  position: relative;
  top: 0;
}

.title-description {
  display: flex;
  flex-direction: column;
  text-align: right;
  margin-bottom: 30px;
  gap: 8px;
}

.description-line {
  font-size: 18px;
  font-weight: 500;
  color: rgba(255, 255, 255, 0.9);
  line-height: 1.5;
}

.features-grid {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-left: 80px;
  position: relative;
}

.feature-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 12px;
  padding: 20px 25px;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  cursor: pointer;
  position: relative;
  overflow: hidden;
  margin-left: 0;
  width: calc(100% - 200px);
}

/* 阶梯排列 */
.feature-card:nth-child(1) { margin-left: 160px; }
.feature-card:nth-child(2) { margin-left: 120px; }
.feature-card:nth-child(3) { margin-left: 80px; }
.feature-card:nth-child(4) { margin-left: 40px; }
.feature-card:nth-child(5) { margin-left: 0px; }

.feature-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.6s;
}

.feature-card:hover::before {
  left: 100%;
}

.feature-card:hover {
  transform: translateY(-8px) scale(1.02) !important;
  background: rgba(255, 255, 255, 0.15);
  border-color: rgba(255, 255, 255, 0.4);
  box-shadow: 
    0 15px 30px rgba(0, 0, 0, 0.3),
    0 0 0 2px rgba(255, 255, 255, 0.1);
}

.feature-content {
  position: relative;
  z-index: 2;
}

.feature-value {
  font-size: 24px;
  font-weight: 700;
  margin-bottom: 8px;
  color: white;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.feature-label {
  font-size: 14px;
  color: rgba(255, 255, 255, 0.9);
  font-weight: 500;
}

/* 响应式设计 */
@media (max-width: 968px) {
  .features-container {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .product-image {
    max-width: 300px;
    height: 250px;
  }
  
  .section-title {
    text-align: center;
  }
  
  .section-title::after {
    left: 50%;
    transform: translateX(-50%);
  }
}

@media (max-width: 768px) {
  .product-features {
    padding: 60px 0;
  }
  
  .feature-card {
    width: calc(100% - 20px);
    padding: 15px 20px;
  }
  
  /* 移动端减少阶梯偏移 */
  .feature-card:nth-child(1) { margin-left: 40px; }
  .feature-card:nth-child(2) { margin-left: 30px; }
  .feature-card:nth-child(3) { margin-left: 20px; }
  .feature-card:nth-child(4) { margin-left: 10px; }
  .feature-card:nth-child(5) { margin-left: 0px; }
}

@media (max-width: 480px) {
  .features-container {
    padding: 0 15px;
  }
  
  .feature-card {
    width: 100%;
    margin-left: 0 !important;
    transform: none !important;
  }
  
  .feature-card:hover {
    transform: translateY(-5px) scale(1.02) !important;
  }
  
  .feature-value {
    font-size: 20px;
  }
}
</style>