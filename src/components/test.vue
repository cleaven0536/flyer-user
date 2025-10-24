<template>
  <section class="multi-scenario">
    <h2 class="section-title">多场景应用</h2>
    <div class="scenario-cards">
      <div 
        v-for="scenario in scenarios" 
        :key="scenario.id" 
        class="scenario-card"
      >
        <div class="scenario-image">{{ scenario.title }}场景</div>
        <div class="scenario-content">
          <h3 class="scenario-title">{{ scenario.title }}</h3>
          <p>{{ scenario.description }}</p>
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
          description: '云端协同智慧物联系统'
        },
        {
          id: 2,
          title: '日常商用',
          description: '提供定制化批量化的空中物流配送服务'
        },
        {
          id: 3,
          title: '定制配送',
          description: '提供搭载冷凝仓医疗仓等特殊设备'
        },
        {
          id: 4,
          title: '农业应用',
          description: '突发事件下提供免费的应急物资'
        }
      ]
    }
  }
}
</script>

<style scoped>
.multi-scenario {
  margin: 40px 0;
}

.scenario-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.scenario-card {
  background-color: #fff;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0,0,0,0.05);
  transition: transform 0.3s, box-shadow 0.3s;
}

.scenario-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.1);
}

.scenario-image {
  height: 160px;
  background-color: #e0e0e0;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #666;
  font-weight: bold;
}

.scenario-content {
  padding: 20px;
}

.scenario-title {
  font-size: 18px;
  margin-bottom: 10px;
  color: #333;
}

.scenario-content p {
  color: #666;
  font-size: 14px;
  line-height: 1.5;
}

@media (max-width: 768px) {
  .multi-scenario {
    margin: 20px 0;
  }
  
  .scenario-cards {
    grid-template-columns: 1fr;
  }
}
</style>