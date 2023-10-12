<script>
export default {
  data() {
    return {
      interval: null,
      currentIndex: 0,
    };
  },
  mounted() {
    const bannerImages = document.querySelector('.banner-images');
    const prevButton = document.querySelector('.prev-button');
    const nextButton = document.querySelector('.next-button');


    nextButton.addEventListener('click', () => {
      this.currentIndex = (this.currentIndex + 1) % 2; 
      const offset = -currentIndex * 100;
      bannerImages.style.transform = `translateX(${offset}%)`;
    });

    prevButton.addEventListener('click', () => {
      this.currentIndex = (this.currentIndex - 1 + 2) % 2;
      const offset = -currentIndex * 100;
      bannerImages.style.transform = `translateX(${offset}%)`;
    });
    this.startAutoChange();
    
  },
  beforeDestroy() {
  this.stopAutoChange();
},
  methods: {
    startAutoChange() {
      this.interval = setInterval(this.nextImage, 5000); // 5000ms (5 segundos)
    },

    stopAutoChange() {
      clearInterval(this.interval);
    },

    nextImage() {
      this.currentIndex = (this.currentIndex + 1) % 2;
      const offset = -this.currentIndex * 100;
      const bannerImages = document.querySelector('.banner-images'); // Add this line
      bannerImages.style.transform = `translateX(${offset}%)`;
    },
  },
};
</script>

<template>
    <section class="banner">
      <div class="banner-images">
        <img src="/banner3.jpg" alt="Banner Image" class="banner-image" />
        <img src="/banner4.jpg" alt="Banner Image 2" class="banner-image" />
      </div>
      <button class="prev-button">&lt;</button>
      <button class="next-button">&gt;</button>
      
    </section>
</template>

<style>
    .banner {
  width: 100%;
  overflow: hidden;
  position: relative;
}

.banner-images {
  display: flex;
  width: 100%;
  position: relative;
  
}

.banner-images .banner-image {
  width: 100%;
  height: auto;
  flex-shrink: 0;
}

.prev-button,
.next-button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: transparent;
  border: none;
  font-size: 24px;
  cursor: pointer;
}

@media (min-width: 1024px) {
  .banner {
  width: 100%;
  overflow: hidden;
  position: relative;
}

.banner-images {
  display: flex;
  width: 100%;
  position: relative;
  height: 500px;
}

.banner-images .banner-image {
  width: 100%;
  height: auto;
  flex-shrink: 0;
  max-height: 500px;
  object-fit: cover;
}

}
.prev-button {
  left: 10px;
}

.next-button {
  right: 10px;
}
</style>