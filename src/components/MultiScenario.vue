<template>
  <section class="multi-scenario">
    <div class="scenario-container">
      <h2 class="section-title">主要应用</h2>
      <div class="scenario-cards">
        <div 
          v-for="scenario in scenarios" 
          :key="scenario.id" 
          class="scenario-card"
        >
          <div class="scenario-image" :style="{ backgroundColor: scenario.color }">
            <div class="scenario-overlay">
              <h3 class="scenario-title">{{ scenario.title }}</h3>
              <p class="scenario-description">{{ scenario.description }}</p>
              <a :href="scenario.link" class="enter-button" @click.prevent="handleEnter(scenario)">
                ENTER
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'MultiScenario',
  data() {
    return {
      scenarios: [
        {
          id: 1,
          title: '平急两用',
          description: '云端协同智慧物联系统',
          color: '#3498db',
          link: '#'
        },
        {
          id: 2,
          title: '日常商用',
          description: '提供定制化批量化的空中物流配送服务',
          color: '#2ecc71',
          link: '#'
        },
        {
          id: 3,
          title: '定制配送',
          description: '提供搭载冷凝仓医疗仓等特殊设备',
          color: '#e74c3c',
          link: '#'
        },
        {
          id: 4,
          title: '农业应用',
          description: '突发事件下提供免费的应急物资',
          color: '#f39c12',
          link: '#'
        }
      ]
    }
  },
  methods: {
    handleEnter(scenario) {
      console.log(`进入 ${scenario.title} 场景`);
      // 这里可以添加路由跳转或其他逻辑
    }
  }
}
</script>

<style scoped>
.multi-scenario {
  background: linear-gradient(135deg, #fffa91 0%, #94f38c 100%);
  margin: 0;
  padding: 20px 0 80px;
  position: relative;
  overflow: hidden;
}

.scenario-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.section-title {
  font-size: 36px;
  font-weight: 700;
  color: white;
  text-align: center;
  margin-bottom: 60px;
  text-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 4px;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 2px;
}

.scenario-cards {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(2, 1fr);
  gap: 30px;
  aspect-ratio: 3 / 2; 
  max-width: 800px;
  margin: 0 auto;
}

.scenario-card {
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
  transition: box-shadow 0.3s ease;
}

.scenario-card:hover {
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
}

.scenario-image {
  height: 100%;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.scenario-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
    135deg,
    rgba(0, 0, 0, 0.3) 0%,
    rgba(0, 0, 0, 0.6) 100%
  );
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  padding: 30px;
  text-align: center;
  color: white;
}

.scenario-title {
  font-size: 28px;
  font-weight: 700;
  margin-bottom: 15px;
  text-shadow: 0 0 2px rgba(0, 0, 0, 0.5);
}

.scenario-description {
  font-size: 12px;
  max-width: 120px;
  line-height: 1.6;
  margin-bottom: 25px;
  text-shadow: 0 1px 1px rgba(0, 0, 0, 0.5);
  opacity: 0.9;
}

.enter-button {
  display: inline-block;
  background: rgba(255, 255, 255, 0.9);
  color: #2c3e50;
  padding: 8px 20px;
  border-radius: 25px;
  font-size: 16px;
  font-weight: 600;
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 1px;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  border: 2px solid transparent;
  cursor: pointer;
}

/* ENTER 按钮的悬停动画 */
.enter-button:hover {
  background: white;
  color: #d6d3d3;
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
  border-color: rgba(255, 255, 255, 0.5);
}

/* 响应式设计 */
@media (max-width: 968px) {
  .multi-scenario {
    padding: 60px 0;
  }
  
  .section-title {
    font-size: 32px;
    margin-bottom: 50px;
  }
  
  .scenario-cards {
    gap: 25px;
    max-width: 700px;
  }
  
  .scenario-title {
    font-size: 24px;
  }
  
  .scenario-description {
    font-size: 15px;
  }
}

@media (max-width: 768px) {
  .multi-scenario {
    padding: 50px 0;
  }
  
  .scenario-container {
    padding: 0 15px;
  }
  
  .section-title {
    font-size: 28px;
    margin-bottom: 40px;
  }
  
  .scenario-cards {
    gap: 20px;
    max-width: 600px;
  }
  
  .scenario-title {
    font-size: 22px;
  }
  
  .scenario-description {
    font-size: 14px;
    margin-bottom: 20px;
  }
  
  .enter-button {
    padding: 10px 25px;
    font-size: 14px;
  }
  
  .enter-button:hover {
    transform: translateY(-3px) scale(1.03);
  }
}

@media (max-width: 600px) {
  .scenario-cards {
    aspect-ratio: 1 / 1.2;
    gap: 15px;
  }
  
  .scenario-overlay {
    padding: 20px;
  }
}

@media (max-width: 480px) {
  .multi-scenario {
    padding: 40px 0;
  }
  
  .section-title {
    font-size: 24px;
    margin-bottom: 30px;
  }
  
  .scenario-cards {
    gap: 12px;
    max-width: 100%;
  }
  
  .scenario-overlay {
    padding: 15px;
  }
  
  .scenario-title {
    font-size: 18px;
    margin-bottom: 10px;
  }
  
  .scenario-description {
    font-size: 12px;
    margin-bottom: 15px;
  }
  
  .enter-button {
    padding: 8px 20px;
    font-size: 12px;
  }
  
  .enter-button:hover {
    transform: translateY(-2px) scale(1.02);
  }
}
</style>