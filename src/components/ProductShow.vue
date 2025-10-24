<template>
  <section class="product-showcase">

    <!-- 上半部分 -->
    <div class="product-section top-section">
      <div class="product-content">
        <!-- 产品 -->
        <div class="product-image-container">
          <div class="product-image">
            <div class="image-placeholder">{{ products[0].name }}</div>
          </div>
        </div>
        
        <!-- 特性 -->
        <div class="product-info-container">
          <div class="product-info">
            <h3 class="product-name-up">{{ products[0].name }}</h3>
            <div class="product-specs">
              <div 
                v-for="spec in products[0].specs" 
                :key="spec.label" 
                class="spec-item"
              >
                <div class="spec-icon" :style="{ backgroundColor: spec.color }"></div>
                <div class="spec-content">
                  <span class="spec-label">{{ spec.label }}</span>
                  <span class="spec-value">{{ spec.value }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- 下半部分 -->
    <div class="product-section bottom-section">
      <div class="product-content reverse">
        <!-- 图片区域 -->
        <div class="product-image-container">
          <div class="product-image">
            <div class="image-placeholder">{{ products[1].name }}</div>
          </div>
        </div>
        
        <!-- 描述区域 -->
        <div class="product-info-container down-side">
          <div class="product-info">
            <h3 class="product-name-down">{{ products[1].name }}</h3>
            <div class="product-specs">
              <div 
                v-for="spec in products[1].specs" 
                :key="spec.label" 
                class="spec-item"
              >
                <div class="spec-icon" :style="{ backgroundColor: spec.color }"></div>
                <div class="spec-content">
                  <span class="spec-label">{{ spec.label }}</span>
                  <span class="spec-value">{{ spec.value }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProductShow',
  data() {
    return {
      products: [
        {
          id: 1,
          name: 'DJI FC30(单电)',
          specs: [
            { label: '产品轴距', value: '2200mm', color: '#3498db' },
            { label: '产品重量', value: '55kg', color: '#f39c12' },
            { label: '起飞重量', value: '95kg', color: '#1abc9c' },
            { label: '飞行时间', value: '15min', color: '#2ecc71' },
            { label: '巡航速度', value: '15m/s', color: '#e74c3c' },
            { label: '产品载重', value: '40kg', color: '#9b59b6' },
          ]
        },
        {
          id: 2,
          name: 'DJI FC30(双电)',
          specs: [
            { label: '产品载重', value: '30kg', color: '#3498db' },
            { label: '巡航速度', value: '15m/s', color: '#e74c3c' },
            { label: '飞行时间', value: '39min', color: '#2ecc71' },
            { label: '起飞重量', value: '95kg', color: '#1abc9c' },
            { label: '产品重量', value: '65kg', color: '#f39c12' },
            { label: '产品轴距', value: '2200mm', color: '#9b59b6' },
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
.product-showcase {
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  margin: 0;
  padding: 30px 0;
  position: relative;
  overflow: hidden;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* 产品区块样式 */
.product-section {
  flex: 1;
  display: flex;
  align-items: center;
  min-height: 50vh;
}

.top-section {
  padding-bottom: 10px;
}

.bottom-section {
  padding-top: 10px;
}

.product-content {
  max-width: 1400px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
  align-items: center;
  padding: 0 20px;
  width: 100%;
}

/* 反转布局：下半部分图片在右，内容在左 */
.product-content.reverse {
  direction: rtl;
}

.product-content.reverse > * {
  direction: ltr;
}

/* 图片容器样式 */
.product-image-container {
  position: relative;
}

.product-image {
  width: 100%;
  height: 300px;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.image-placeholder {
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, #3498db, #2ecc71);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  color: white;
  font-weight: 600;
}

/* 信息容器样式 */
.product-info-container {
  display: flex;
  padding: 0 20px;
}

.down-side {
 justify-content: flex-end;
}

.product-info {
  max-width: 650px;
}

.product-name-up {
  font-size: 32px;
  font-weight: 700;
  color: #2c3e50;
  margin-bottom: 40px;
  text-align: left;
}
.product-name-down {
  font-size: 32px;
  font-weight: 700;
  color: #2c3e50;
  margin-bottom: 40px;
  text-align: right;
}

/* 规格列表样式 */
.product-specs {
  display: flex;
  flex-wrap: nowrap;
  gap: 50px;
}

.spec-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 12px;
  padding: 0;
  background: transparent;
}


.spec-icon {
  width: 60px;
  height: 60px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.spec-content {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.spec-label {
  font-size: 14px;
  color: #7f8c8d;
  font-weight: 500;
}

.spec-value {
  font-size: 18px;
  font-weight: 700;
  color: #2c3e50;
}

/* 响应式设计 */
@media (max-width: 968px) {
  .product-content {
    grid-template-columns: 1fr;
    gap: 40px;
    padding: 0 20px;
  }
  
  .product-content.reverse {
    direction: ltr;
  }
  
  .product-image {
    height: 250px;
  }
  
  .product-specs {
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
  }
  
  .product-section {
    min-height: auto;
    padding: 40px 0;
  }
}

@media (max-width: 768px) {
  .product-showcase {
    padding: 40px 0;
    min-height: auto;
  }
  
  .product-name {
    font-size: 24px;
    margin-bottom: 30px;
  }
  
  .product-specs {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .spec-item {
    flex-direction: row;
    text-align: left;
    gap: 16px;
  }
  
  .spec-icon {
    width: 50px;
    height: 50px;
    flex-shrink: 0;
  }
}

@media (max-width: 480px) {
  .product-content {
    padding: 0 15px;
    gap: 30px;
  }
  
  .product-image {
    height: 200px;
  }
  
  .product-info-container {
    padding: 0 10px;
  }
  
  .spec-item {
    gap: 12px;
  }
  
  .spec-icon {
    width: 40px;
    height: 40px;
  }
  
  .spec-value {
    font-size: 16px;
  }
}
</style>