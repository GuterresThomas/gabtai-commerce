<template>
  <h1 className="chamada">Conheça os produtos Davines</h1> 
  <div class="container">
    <div class="product-grid"> 
      <div class="product-card" v-for="(product, index) in filteredProducts" :key="index">
        <img :src="product.image" :alt="product.name" class="product-image" />
        <h3 class="product-name">{{ product.name }}</h3>
        <p class="product-description">{{ product.description }}</p>
        <p class="product-price">{{ product.price }}</p> 
        <button id="openLinkButton" class="button">Compre agora pelo whatsapp</button>
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
        /* {
          name: "Hair Mask Heart of glass",
          description: "Para todos os tipos de cabelo, livre de parabenos.",
          price: "R$ 279,00",
          image: "/produto1.jpg",
        },
        {
          name: "Smoothing Conditioner Love",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "R$ 239,00",
          image: "/produto8.jpg",
        },
        {
          name: "Conditioner Nourishing",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "R$ 250,00",
          image: "/produto13.jpg",
        },
        {
          name: "Mask Vegetaria Miracle Nourishing",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "R$ 250,00",
          image: "/produto14.webp",
        },
        {
          name: "Smoothing Shampoo Love",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "R$ 219,00",
          image: "/produto9.jpg",
        },
        {
          name: "Shampoo Bar Dede",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "R$ 250,00",
          image: "/produto21.jpg",
        }, 
         {
          name: "Hair Mask Nounou",
          description: "Para todos os tipos de cabelo, livre de parabenos",
          price: "R$ 250,00",
          image: "/produto17.jpg",
        },
        */
        {
          name: "Oi oil 50 ml",
          description: "Óleo para todos os cabelos, sem parabenos. Nutrição profunda.",
          price: "R$ 219,90",
          image: "/produto2.jpg",
        },
        {
          name: "Oi shampoo 280ml",
          description: "Shampoo nutritivo para todos os tipos de cabelo.",
          price: "R$ 199,00",
          image: "/produto3.jpg",
        },
        {
          name: "Oi conditioner 250ml",
          description: " Condicionador de cabelo para hidratação profunda.",
          price: "R$ 239,90",
          image: "/produto4.jpg",
        },
        {
          name: "Hair Butter Oi 250ml",
          description: "Manteiga capilar para nutrição intensa.",
          price: "R$ 289,90",
          image: "/produto18.jpg",
        },
        {
          name: "Oi all in one milk 50ml",
          description: "Leave-in capilar versátil para todos os cabelos.",
          price: "R$ 179,90",
          image: "/produto23.jpg",
        },
        {
          name: "Kit travel size Oi 90ml",
          description: "Conjunto de viagem Oi, para nutrição intensa.",
          price: "R$ 179,90",
          image: "/produto20.webp",
        },
        {
          name: "Mask Authentic moisturizing 150g",
          description: "Máscara hidratante para todos os tipos de cabelo.",
          price: "R$ 179,00",
          image: "/produto5.webp",
        },
        {
          name: "Authentic Butter 200g",
          description: "Manteiga para nutrição.",
          price: "R$ 279,90",
          image: "/produto6.jpg",
        },
        {
          name: "Energizing Shampoo 250ml",
          description: "desenvolvido para couro cabeludo frágil e com tendência a queda.",
          price: "R$ 199,90",
          image: "/produto7.webp",
        },
        
        {
          name: "Shampoo Momo 250ml",
          description: "ideal para cabelos secos e desidratados.",
          price: "R$ 189,90",
          image: "/produto11.jpg",
        },

        {
          name: "Conditioner Momo 250ml",
          description: "ideal para cabelos secos e desidratados, proporciona brilho intenso e maciez.",
          price: "R$ 199,90",
          image: "/produto10.jpg",
        },

        {
          name: "Shampoo Bar Momo 100g",
          description: "ideal para cabelos secos e desidratados, proporcionando maciez e brilho.",
          price: "R$ 99,90",
          image: "/produto22.jpg",
        },

        {
          name: "Shampoo Nourishing 250ml",
          description: " Limpa delicadamente proporcionando um efeito nutritivo e revitalizante imediato.",
          price: "R$ 219,00",
          image: "/produto12.jpg",
        },
        {
          name: "Shampoo Nounou 250ml",
          description: "proporciona nutrição profunda, hidratação e devolvendo uma maciez excepcional",
          price: "R$ 179,90",
          image: "/produto15.jpg",
        },
        {
          name: "Conditioner Nounou 250ml",
          description: "proporciona nutrição profunda, hidratação e devolvendo uma maciez excepcional",
          price: "R$ 199,90",
          image: "/produto16.jpg",
        },
        {
          name: "Kit travel size Nounou 75ml",
          description: "proporciona nutrição profunda, hidratação e devolvendo uma maciez excepcional",
          price: "R$ 179,90",
          image: "/produto19.webp",
        },
        

      ],
    };
  },
  mounted() {
    document.getElementById('openLinkButton').addEventListener('click', this.openLink);
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

    openLink () {
      const url = 'https://wa.me/5555981291170';
      window.open(url, '_blank');
    },
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

@media (min-width: 1024px) {
  .product-card {
    display: grid;
    -ms-grid-row-align: center;
    align-items: center;
    border: 1px solid #ddd;
    padding: 10px;
    text-align: center;
    border-radius: 5px;
    max-height: 500px;
    justify-content: center;
    justify-items: center;
  }
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
