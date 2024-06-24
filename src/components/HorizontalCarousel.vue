<template>
  <div>
  <div class="carousel">
    <div class="carousel-inner" :style="{ width: `${100 * items.length}%` }">
      <div class="carousel-item" v-for="(item, index) in items" :key="index" :style="{ width: `${100 / items.length}%` }">
        <div v-if="item.type === 'text'">
          <div v-html="item.content"></div>
        </div>
        <div v-else-if="item.type === 'image'">
          <img :src="item.src" alt="carousel-image">
        </div>
        <div v-else-if="item.type === 'input'">
          <input v-model="item.value" :placeholder="item.placeholder">
          <span v-if="item.error" class="error-message">{{ item.error }}</span>
        </div>
        <div v-else-if="item.type === 'video'">
          <video :src="item.src" controls></video>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
    export default {
      name: 'HorizontalCarousel',
  props: {
    items:{
      type: Array, 
      required: true 
    },
  }
    }
</script>

<style lang="scss" scoped>
  .carousel {
  overflow: hidden;
}

.carousel-inner {
  display: flex;
  transition: transform 0.5s ease;
}

.carousel-item {
  flex: 0 0 auto;
}
</style>