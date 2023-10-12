<script setup lang="ts">
import HelloWorld from './components/HelloMessage.vue';
import ProductGrid from './components/ProductGrid.vue';
import Footer from './components/footer.vue'
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
    <Footer />
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
</style>
