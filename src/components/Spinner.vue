<script>
export default {
  name: "Spinner",
  data() {
    return {
      imagesLoaded: false,
      totalImages: 0,
      loadedImages: 0,
    };
  },
  methods: {
    onImageLoad() {
      this.loadedImages++;
      if (this.loadedImages === this.totalImages) {
        this.imagesLoaded = true; // Oculta el spinner cuando todas las imágenes están cargadas
      }
    },
  },
  mounted() {
    const images = this.$el.querySelectorAll("img");
    this.totalImages = images.length;

    if (this.totalImages === 0) {
      this.imagesLoaded = true; // No hay imágenes, oculta el spinner
    } else {
      images.forEach((img) => {
        img.addEventListener("load", this.onImageLoad);
        if (img.complete) {
          this.onImageLoad();
        }
      });
    }
  }
};
</script>

<template>
  <div>
    <div v-if="!imagesLoaded" class="overlay">
      <div class="spinner"></div>
    </div>
    <div v-if="imagesLoaded">
      <slot></slot>
    </div>
  </div>
</template>

<style>
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgb(0, 0, 0); /* Pantalla oscura */
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999; /* Asegura que esté por encima de otros elementos */
}

.spinner {
  border: 16px solid #f3f3f3;
  border-radius: 50%;
  border-top: 16px solid #3498db;
  width: 120px;
  height: 120px;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
