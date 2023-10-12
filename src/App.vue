<script setup lang="ts">
import HelloWorld from './components/HelloMessage.vue';
import ProductGrid from './components/ProductGrid.vue';

import Banner from './components/Banner.vue';
import TextDavines from './components/TextDavines.vue'
</script>

<template>
  <header>
    <img alt="logo" class="logo" src="./assets/output.png" width="150" height="150" />

    <div class="wrapper">
      <HelloWorld msg="Bem-vinda ao Gabtai Commerce!" />
    </div>
  </header>
  <Banner/>
  <main>
    <ProductGrid/>
  </main>
  <div class="banner-container">
    <img class="banner-container-image" src="/banner3.jpg" />
  </div>
  <div>
    <TextDavines/>
  </div>
  <footer>
      <div class="footer-content">
        <p>Copyright © 2023 Gabtai.com.br. Todos os direitos reservados.</p>
      </div>
  </footer>
</template>

<style scoped>
header {
  line-height: 1.5;
  margin-bottom: 1rem;
  box-shadow: 1px 1px 3px 2px #333;
  background-color: rgb(4, 77, 137);
  padding: 1rem;
}

.logo {
  display: block;
  margin: 0 auto;
}

.banner-container {
  width: 100%;
  max-height: 500px;

}

.banner-container-image {
  max-height: 400px;
  object-fit:contain;
  width: 100%;
}



@media (min-width: 1024px) {
  header {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(4, 77, 137);
    
    padding-right: calc(var(--section-gap) / 2);
  }


  .logo {
    margin: 0 0 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .banner-container {
  width: 100%;
  max-height: 500px;

}

.banner-container-image {
  max-height: 400px;
  object-fit:none;
  width: 100%;
}

}

footer {
    background-color: rgb(4, 77, 137);
    color: white;
    padding: 20px 0;
    text-align: center;
    margin-bottom: 0;
    
    width: 100%;
    display: flex;
  }
  
  .footer-content {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .footer-content p {
    margin: 0;
    font-size: 16px;
  }
  
  .footer-content ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  .footer-content li {
    display: inline;
    margin-right: 20px;
  }
  
  .footer-content a {
    color: #fff;
    text-decoration: none;
    font-size: 16px;
  }
</style>
