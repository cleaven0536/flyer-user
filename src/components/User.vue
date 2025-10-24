<template>
  <section class="user-section">
    <div class="user-content">
      <!-- 第一段文字 - 企业用户 -->
      <div class="text-block enterprise-text">
        <h3 class="text-title">企业用户：</h3>
        <p class="text-desc">日常供应——提供一站式批量物资配送服务，客户可在线完成下单，申请冷链或医药等特质化运输，以及实时追踪订单状态等操作</p>
      </div>
      
      <!-- 第二段文字 - 救援人员 -->
      <div class="text-block rescue-text">
        <h3 class="text-title">救援人员：</h3>
        <p class="text-desc">应急救援——此界面则面向经过认证的救援人员或机构，其简化了任务提交流程，支持快速发起紧急物资配送请求，并通过内置的AI助手。直观掌握救援物资的实时动态。</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'User'
}
</script>

<style scoped>
.user-section {
  background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
  margin: 0;
  padding: 0;
  position: relative;
  overflow: hidden;
  height: 50vh; /* 屏幕高度的2/3 */
  display: flex;
  align-items: center;
  justify-content: center;
}

.user-content {
  position: relative;
  width: 100%;
  max-width: 1200px;
  height: 100%;
  margin: 0 auto;
  padding: 0 40px;
}

/* 文字块通用样式 */
.text-block {
  position: absolute;
  color: white;
  text-align: left;
  line-height: 1.4;
}

.text-title {
  font-size: 32px;
  font-weight: 700;
  margin: 0 0 12px 0;
  text-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
}

.text-desc {
  font-size: 16px;
  font-weight: 400;
  max-width: 350px; 
  word-wrap: break-word;
  word-break: break-word;
  margin: 0;
  opacity: 0.9;
  text-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
  line-height: 1.6;
}

.enterprise-text {
  top: 15%;
  left: 20%;
}

/* 第二段文字 */
.rescue-text {
  top: calc(15% + 140px); 
  left: calc(25% + 260px); 
}

/* 响应式设计 */
@media (max-width: 968px) {
  .user-content {
    padding: 0 30px;
    max-width: 800px;
  }
  
  .text-title {
    font-size: 28px;
  }
  
  .text-desc {
    font-size: 18px;
  }
  
  .enterprise-text {
    top: 35%;
    left: 15%;
  }
  
  .rescue-text {
    top: calc(35% + 100px);
    left: calc(15% + 120px);
  }
}

@media (max-width: 768px) {
  .user-section {
    height: 60vh;
  }
  
  .user-content {
    padding: 0 20px;
    max-width: 600px;
  }
  
  .text-title {
    font-size: 24px;
    margin-bottom: 8px;
  }
  
  .text-desc {
    font-size: 16px;
  }
  
  .enterprise-text {
    top: 35%;
    left: 10%;
  }
  
  .rescue-text {
    top: calc(35% + 80px);
    left: calc(10% + 100px);
  }
}

@media (max-width: 480px) {
  .user-section {
    height: 50vh;
  }
  
  .user-content {
    padding: 0 15px;
  }
  
  .text-title {
    font-size: 20px;
  }
  
  .text-desc {
    font-size: 14px;
  }
  
  .enterprise-text {
    top: 30%;
    left: 8%;
  }
  
  .rescue-text {
    top: calc(30% + 60px);
    left: calc(8% + 80px);
  }
}

/* 动画效果 */
.text-block {
  opacity: 0;
  animation: fadeInUp 0.8s ease forwards;
}

.enterprise-text {
  animation-delay: 0.2s;
}

.rescue-text {
  animation-delay: 0.5s;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>