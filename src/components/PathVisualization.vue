<template>
  <section class="path-visualization">
    <div class="visualization-container">
      <h2 class="section-title">路径与轨迹可视化</h2>
      <p class="description">无人机实时控制，提供实时画面查看和状态监控功能</p>
      <div class="visualization-wrapper">
        <div class="optimal-planning-label">OPTIMAL PLANNING</div>
        <div class="visualization-area">
          路径可视化图表区域
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'PathVisualization'
}
</script>

<style scoped>
.path-visualization {
  background: linear-gradient(135deg, #83dbac 0%, #6fbddf 100%);
  margin: 0;
  padding: 80px 0;
  position: relative;
  overflow: hidden;
}

.visualization-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  text-align: center;
}

.section-title {
  font-size: 36px;
  font-weight: 700;
  color: white;
  margin-bottom: 20px;
}

.description {
  font-size: 18px;
  color: rgba(255, 255, 255, 0.9);
  margin-bottom: 40px;
  line-height: 1.6;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.visualization-wrapper {
  position: relative;
  display: inline-block;
  width: 100%;
  transition: all 0.6s cubic-bezier(0.23, 1, 0.32, 1);
}

.visualization-area {
  height: 400px;
  background: linear-gradient(145deg, #ffffff, #f0f0f0);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #666;
  font-weight: 600;
  font-size: 18px;
  box-shadow: 
    0 10px 30px rgba(0, 0, 0, 0.2),
    inset 0 1px 0 rgba(255, 255, 255, 0.8);
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  border: 1px solid rgba(255, 255, 255, 0.3);
  overflow: hidden; 
}

.optimal-planning-label {
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  color: rgb(255, 255, 255);
  background: rgb(139, 175, 183);
  padding: 8px 20px;
  border-radius: 20px;
  font-size: 16px;
  font-weight: 600;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
  z-index: 10;
  white-space: nowrap;
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.visualization-wrapper:hover {
  transform: translateY(-10px) scale(1.02);
  box-shadow: 
    0 12px 30px rgba(0, 0, 0, 0.18),
    0 0 0 1px rgba(255, 255, 255, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.9);
}

/* 响应式设计 */
@media (max-width: 968px) {
  .path-visualization {
    padding: 60px 0;
  }
  
  .section-title {
    font-size: 32px;
  }
  
  .description {
    font-size: 16px;
    margin-bottom: 30px;
  }
  
  .visualization-area {
    height: 350px;
  }
  
  .optimal-planning-label {
    font-size: 14px;
    padding: 6px 16px;
  }
}

@media (max-width: 768px) {
  .path-visualization {
    padding: 50px 0;
  }
  
  .visualization-container {
    padding: 0 15px;
  }
  
  .section-title {
    font-size: 28px;
    margin-bottom: 15px;
  }
  
  .description {
    font-size: 15px;
    margin-bottom: 25px;
  }
  
  .visualization-area {
    height: 300px;
    font-size: 16px;
  }
  
  .visualization-area:hover {
    transform: translateY(-5px) scale(1.01);
  }
  
  .optimal-planning-label {
    font-size: 13px;
    padding: 5px 14px;
    top: -12px;
  }
}

@media (max-width: 480px) {
  .path-visualization {
    padding: 40px 0;
  }
  
  .section-title {
    font-size: 24px;
  }
  
  .description {
    font-size: 14px;
    margin-bottom: 20px;
  }
  
  .visualization-area {
    height: 250px;
    font-size: 14px;
    border-radius: 12px;
  }
  
  .optimal-planning-label {
    font-size: 12px;
    padding: 4px 12px;
    top: -10px;
  }
}
</style>