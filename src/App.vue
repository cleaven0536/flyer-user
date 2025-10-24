<template>
  <div id="app">
    <Header />
    <main class="container">
      <IntroductionArea />
      <User />
      <ProductFeatures />
      <ProductShow />
      <ProductApplication />
      <PathVisualization />
      <MultiScenario />
      <ServiceGuarantee />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import IntroductionArea from './components/IntroductionArea.vue' 
import User from './components/User.vue'
import ProductFeatures from './components/ProductFeatures.vue'
import ProductShow from './components/ProductShow.vue'
import ProductApplication from './components/ProductApplication.vue'
import PathVisualization from './components/PathVisualization.vue'
import MultiScenario from './components/MultiScenario.vue'
import ServiceGuarantee from './components/ServiceGuarantee.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    IntroductionArea,
    User,
    ProductFeatures,
    ProductShow,
    ProductApplication,
    PathVisualization,
    MultiScenario,
    ServiceGuarantee,
    Footer
  }
}
</script>

<style scoped>
#app{
  box-sizing: inherit;
  transition: opacity ease-in 0.2s;
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font-weight: 400;
  vertical-align: baseline;
  background: 0 0;
  position: relative;
  width: auto;
  min-width: 1250px;
  display: flex;
  flex-direction: column;
}
</style>