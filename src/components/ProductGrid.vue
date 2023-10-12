<template>
  <h1 className="chamada">Conheça os produtos Davines</h1> 
  <div class="container">
    <div class="product-grid"> 
      <div class="product-card" v-for="(product, index) in filteredProducts" :key="index">
        <img :src="product.image" :alt="product.name" class="product-image" />
        <h3 class="product-name">{{ product.name }}</h3>
        <p class="product-description">{{ product.description }}</p>
        <p class="product-price">{{ product.price }}</p> 
        <button class="button">Compre agora pelo whatsapp</button>
      </div>
  </div>
  <button class="button-show" v-if="showAllButton" @click="showAllProducts">Ver Todos os produtos</button>
  <button class="button-show" v-if="showAllProductsData" @click="showLessProducts">Ver Menos</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showAllProductsData: false,
      products: [
        {
          name: "Conditioner Heart of glass",
          description: "Para todos os tipos de cabelo, livre de parabenos.",
          price: "$199.99",
          image: "/produto1.jpg",
        },
        {
          name: "Oi oil 50 ml",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "$129.99",
          image: "/produto2.jpg",
        },
        {
          name: "Oi shampoo 280ml",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "$189.99",
          image: "/produto3.jpg",
        },
        {
          name: "Oi conditioner",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "$229.99",
          image: "/produto4.jpg",
        },
        {
          name: "Produto 2",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "$29.99",
          image: "/produto1.jpg",
        },
        {
          name: "Produto 2",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "$29.99",
          image: "/produto1.jpg",
        },
      ],
    };
  },
  computed: {
    filteredProducts() {
      if (this.showAllProductsData) {
        return this.products;
      } else {
        return this.products.slice(0, 4);
      }
    },
    showAllButton() {
      return !this.showAllProductsData && this.products.length > 4;
    },
  },
  methods: {
    showAllProducts() {
      this.showAllProductsData = true;
    },
    showLessProducts() {
      this.showAllProductsData = false;
    },
  },
};
</script>

<style scoped>
.chamada {
    align-items: center;
    display: flex;
    justify-content: center;
    margin: 1rem;
    word-spacing: 2px;
    font-style: italic;
    font-size:x-large;
}
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); /* Grid responsivo */
  gap: 20px;
  margin: 2rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 1rem;
}

.product-card {
  border: 1px solid #ddd;
  padding: 10px;
  text-align: center;
  border-radius: 5px;
  max-height: 500px;
}

.product-image {
  max-width: 100%;
  object-fit: contain;
  max-height: 200px;
  transition: transform 0.2s;
}

.product-image:hover {
  transform: scale(1.1);
}

.product-name {
  font-size: 1.2rem;
  margin: 10px 0;
}

.product-description {
  font-size: 1rem;
  color: #777;
}

.product-price {
  font-size: 1.1rem;
  color: #333;
}

.button-show {
  padding: 0.5rem;
  border-radius: 10px;
  color: white;
  background-color: rgb(4, 77, 137);
  border: none;
  box-shadow: 0px 1px 2px 1px #333;
  font-size: medium;
  cursor: pointer;
  transition: transform 0.2s;
  width: auto;
  margin: 1rem;
}

.button:hover {
  transform: scale(1.1);
}

.button {
  padding: 1rem;
  border-radius: 10px;
  color: white;
  background-color: rgb(4, 77, 137);
  border: none;
  box-shadow: 0px 1px 2px 1px #333;
  font-size: medium;
  font-weight: normal;
  cursor: pointer;
  transition: transform 0.2s;
  margin-bottom: 0;
}
</style>
