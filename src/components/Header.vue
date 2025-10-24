<template>  
    <nav class="site-header" :class="{ 'scrolled': isScrolled }" role="navigation">
    <div class="header-container">

        <!--左侧Logo-->
        <div class="header-logo">
        <a href=" ">
            <img src="../images/无人机 1.png" class="header-logo-img"></img>
        </a>
        </div>

        <!--导航栏-->
        <div class="header-navbar">
            <ul class="navbar-category">

                <li class="nav-option">
                <a href="#" @click.prevent="navigateTo('home')">
                    首页
                </a>
                <div class="dui-dropdown-menu" style="pointer-events: none; height: 0px;"></div>
                </li>

                <li class="nav-option">
                <a href="#" @click.prevent="navigateTo('products')">
                    产品
                </a>
                <div class="dui-dropdown-menu" style="pointer-events: none; height: 0px;"></div>
                </li>

                <li class="nav-option">
                <a href="#" @click.prevent="navigateTo('solutions')">
                    主营业务
                </a>
                <div class="nav-dropdown-menu" style="pointer-events: none; height: 0px;"></div>
                <div class="single-dropdown">
                    <div class="dropdown-container">
                    <ul>
                        <li class="nav-item">
                        <a href="#" 
                            class="nav-item-link">
                            应急救援
                        </a>
                        </li>
                        <li class="nav-item">
                        <a href="#" 
                            class="nav-item-link">
                            智能物流
                        </a>
                        </li>
                    </ul>
                    </div>
                </div>
                </li>

                <li class="nav-option">
                <a href="#" @click.prevent="navigateTo('about')">
                    联系我们
                </a>
                <div class="dui-dropdown-menu" style="pointer-events: none; height: 0px;"></div>
                </li>

                <li class="nav-option">
                <a href="#" @click.prevent="navigateTo('contact')">
                    登录注册
                </a>
                <div class="dui-dropdown-menu" style="pointer-events: none; height: 0px;"></div>
                </li>
            </ul>
        </div>

        <div class="user-ui">
        <a href=" ">
            <img src="../images/人 1.png" class="user-ui-img"></img>
        </a>
        </div>
    </div>
    </nav>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      isScrolled: false
    }
  },
  methods: {
    navigateTo(section) {
      console.log(`导航到: ${section}`);
    },
    handleScroll() {
      // 当滚动超过10px时添加背景
      this.isScrolled = window.scrollY > 10;
    }
  },
  mounted() {
    // 添加滚动监听
    window.addEventListener('scroll', this.handleScroll);
    // 初始化检查
    this.handleScroll();
  },
  beforeUnmount() {
    // 移除滚动监听
    window.removeEventListener('scroll', this.handleScroll);
  }
}
</script>

<style scoped>
.site-header{
    box-sizing: inherit;
    padding: 0;
    font-size: 100%;
    font-weight: 400;
    vertical-align: baseline;
    border: 0;
    margin: auto;
    -webkit-font-smoothing: antialiased;
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    z-index: 900;
    height: 52px;
    display: flex;
    justify-content: center;
    min-width: 1250px;
    
    /* 初始状态：透明背景 */
    background: rgba(255, 255, 255, 0);
    backdrop-filter: none;
    transition: all 0.3s ease;
}

/* 滚动时的状态 */
.site-header.scrolled {
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(10px);
    box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
    border-bottom: 1px solid rgba(0, 0, 0, 0.05);
}

.header-container {
    box-sizing: inherit;
    padding: 0;
    border: 0;
    font-size: 100%;
    font-weight: 400;
    vertical-align: baseline;
    background: 0 0;
    margin: 0 auto;
    height: 100%;
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    width: 100%;
}

.header-navbar {
    box-sizing: inherit;
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font-weight: 400;
    vertical-align: baseline;
    background: 0 0;
    flex: 1;
    display: flex;
    justify-content: flex-end;
    flex-flow: row nowrap;
    opacity: 1;
    width: 80%;
}

.header-logo {
  height: 52px;
  width: auto;
  align-self: flex-start;
}

.header-logo-img {
  display: block;
  height: 100%;
  width: auto;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
  background-color: transparent;
  margin-left: 50px;
}
.navbar-category {
  list-style: none;
  display: flex;
  gap: 160px;
  margin: 0;
  padding: 0;
  margin-right: 100px;
}

.nav-item{
    list-style-type: none;
}

/* 导航链接样式 */
.nav-option a {
    color: #333;
    text-decoration: none;
    padding: 12px 0;
    transition: color 0.3s ease;
    position: relative;
}

/* 滚动时链接颜色保持不变，或者可以调整透明度 */
.site-header:not(.scrolled) .nav-option a {
    color: #333;
}

.nav-option a:hover {
    color: #007bff;
}

/* 下拉菜单样式 */
.single-dropdown {
    position: absolute;
    top: 100%;
    left: 55%;
    background: white;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    border-radius: 4px;
    opacity: 0;
    visibility: hidden;
    transform: translateY(-10px);
    transition: all 0.3s ease;
    min-width: 160px;
}

.nav-option:hover .single-dropdown {
    opacity: 1;
    visibility: visible;
    transform: translateY(0);
}

.nav-item-link {
    display: block;
    padding: 12px 16px;
    color: #333;
    text-decoration: none;
    transition: background-color 0.3s ease;
}

.nav-item-link:hover {
    background-color: #f8f9fa;
    color: #007bff;
}

/* 右侧UI图标样式 */
.user-ui {
    margin-right: 50px;
}

.user-ui-img {
    display: block;
    height: 52px;
    width: auto;
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
}
</style>