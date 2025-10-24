<template>
  <section class="product-application">
    <div class="application-container">
      <!-- 左侧文字区域 -->
      <div class="application-text">
        <h2 class="application-title">应用场景</h2>
        <p class="application-subtitle">解决特定情境下的效率瓶颈</p>
      </div>
      
      <!-- 右侧图片区域 -->
      <div class="application-image">
        <div class="image-placeholder">应用场景示意图</div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProductApplication'
}
</script>

<style scoped>
.product-application {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  margin: 0;
  padding: 80px 0;
  position: relative;
  overflow: hidden;
  min-height: 400px;
  display: flex;
  align-items: center;
}

.application-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
  padding: 0 40px;
  width: 100%;
}

/* 左侧文字样式 */
.application-text {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.application-title {
  font-size: 48px;
  font-weight: 700;
  color: white;
  line-height: 1.1;
  margin: 0;
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
}

.application-subtitle {
  font-size: 24px;
  font-weight: 400;
  color: rgba(255, 255, 255, 0.9);
  line-height: 1.4;
  margin: 0;
  max-width: 400px;
}

/* 右侧图片样式 */
.application-image {
  width: 100%;
  height: 300px;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.application-image:hover {
  transform: translateY(-5px);
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
}

.image-placeholder {
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, #ff6b6b, #ffa726);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  color: white;
  font-weight: 600;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

/* 响应式设计 */
@media (max-width: 968px) {
  .application-container {
    grid-template-columns: 1fr;
    gap: 40px;
    padding: 0 20px;
    text-align: center;
  }
  
  .application-text {
    align-items: center;
  }
  
  .application-title {
    font-size: 36px;
  }
  
  .application-subtitle {
    font-size: 20px;
  }
  
  .application-image {
    height: 250px;
    order: -1; /* 移动端图片在上方 */
  }
}

@media (max-width: 768px) {
  .product-application {
    padding: 60px 0;
    min-height: 350px;
  }
  
  .application-title {
    font-size: 32px;
  }
  
  .application-subtitle {
    font-size: 18px;
  }
  
  .application-image {
    height: 200px;
  }
}

@media (max-width: 480px) {
  .product-application {
    padding: 40px 0;
    min-height: 300px;
  }
  
  .application-container {
    padding: 0 15px;
    gap: 30px;
  }
  
  .application-title {
    font-size: 28px;
  }
  
  .application-subtitle {
    font-size: 16px;
  }
  
  .application-image {
    height: 180px;
  }
  
  .image-placeholder {
    font-size: 16px;
  }
}
</style>