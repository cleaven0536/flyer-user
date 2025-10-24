<template>
  <section class="service-guarantee">
    <div class="guarantee-container">
      <h2 class="section-title">服务保障</h2>
      <div class="guarantee-content">
        <p class="highlight-text">我们为所有商业运输服务提供全面的货物安全保障。当物品在运输过程中发生损坏或遗失，一经核实即按服务合同中的约定标准进行赔付。客户可选择保价服务，以获得更高额度的保障。</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ServiceGuarantee'
}
</script>

<style scoped>
.service-guarantee {
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  margin: 0;
  padding: 80px 0;
  position: relative;
  overflow: hidden;
}

.guarantee-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  flex-direction: column;
  text-align: center;
}

.section-title {
  font-size: 42px;
  font-weight: 700;
  color: #bfe4ea;
  margin-bottom: 40px;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
  width: 120px;
  height: 4px;
  background: #b8d1d1;
  border-radius: 2px;
}

.guarantee-content {
  line-height: 1.8;
  align-items: center;
  justify-content: center;
  border-radius: 12px;
  background-color: #bcbcc4;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
}

.highlight-text {  
  padding: 25px 30px;
  font-size: 26px;
  color: #bfe4ea;
  line-height: 1.7;
  margin: 0 30px;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .service-guarantee {
    padding: 60px 0;
  }
  
  .guarantee-container {
    padding: 0 15px;
  }
  
  .section-title {
    font-size: 28px;
    margin-bottom: 30px;
  }
  
  .highlight-text {
    font-size: 16px;
    padding: 20px;
  }
  
  .highlight-text::before {
    top: -12px;
    font-size: 14px;
    padding: 4px 12px;
  }
}

@media (max-width: 480px) {
  .service-guarantee {
    padding: 40px 0;
  }
  
  .section-title {
    font-size: 24px;
  }
  
  .highlight-text {
    font-size: 15px;
    padding: 15px;
  }
  
  .highlight-text::before {
    top: -10px;
    font-size: 12px;
    padding: 3px 10px;
  }
}
</style>