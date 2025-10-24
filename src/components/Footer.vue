<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-section">
          <h3>飞天物联</h3>
          <p>SkyLink Technologies</p>
          <p>领先的无人机物流解决方案提供商</p>
        </div>
        <div class="footer-section">
          <h3>联系我们</h3>
          <p>电话: 400-123-4567</p>
          <p>邮箱: contact@flywise.com</p>
          <p>地址: 广东省佛山市华南师范大学</p>
        </div>
        <div class="footer-section">
          <h3>关注我们</h3>
          <p>微信公众号: 飞天物联</p>
          <p>微博: @飞天物联官方微博</p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2025 飞天物联科技有限公司 版权所有</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
.footer {
  background: linear-gradient(135deg, #1a2530 0%, #2c3e50 100%);
  color: #fff;
  padding: 60px 0 20px 0;
  margin: 0;
  position: relative;
  overflow: hidden;
}

.footer::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  margin-bottom: 40px;
}

.footer-section h3 {
  margin-bottom: 20px;
  font-size: 20px;
  font-weight: 600;
  color: #fff;
  position: relative;
}

.footer-section h3::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 0;
  width: 30px;
  height: 2px;
  background: #3498db;
  border-radius: 1px;
}

.footer-section p {
  color: #bdc3c7;
  margin-bottom: 12px;
  line-height: 1.6;
  font-size: 14px;
}

.footer-section p:first-of-type {
  color: #ecf0f1;
  font-weight: 500;
}

.footer-bottom {
  text-align: center;
  padding-top: 30px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-bottom p {
  color: #95a5a6;
  font-size: 14px;
  margin: 0;
}

/* 悬停效果 */
.footer-section p:hover {
  color: #3498db;
  transition: color 0.3s ease;
  cursor: default;
}

/* 响应式设计 */
@media (max-width: 968px) {
  .footer-content {
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
  }
}

@media (max-width: 768px) {
  .footer {
    padding: 40px 0 15px 0;
  }
  
  .container {
    padding: 0 15px;
  }
  
  .footer-content {
    grid-template-columns: 1fr;
    gap: 25px;
    margin-bottom: 30px;
  }
  
  .footer-section h3 {
    font-size: 18px;
    margin-bottom: 15px;
  }
  
  .footer-section p {
    font-size: 13px;
    margin-bottom: 10px;
  }
  
  .footer-bottom {
    padding-top: 20px;
  }
  
  .footer-bottom p {
    font-size: 12px;
  }
}

@media (max-width: 480px) {
  .footer {
    padding: 30px 0 10px 0;
  }
  
  .footer-content {
    gap: 20px;
  }
  
  .footer-section h3 {
    font-size: 16px;
  }
  
  .footer-section p {
    font-size: 12px;
  }
}
</style>