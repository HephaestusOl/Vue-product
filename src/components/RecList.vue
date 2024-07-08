<template>
  <div class="recommendation">
    <div class="recommendation__text text">
      <h2 class="text__title">Recommend</h2>
      <p class="text__description">See all</p>
    </div>
    <ul class="recommendation__list list">
      <li v-for="product in products" :key="product.id" class="list__item item">
        <a href="#">
          <div class="item__wrapper">
            <div class="tags">
              <span v-for="(tag, index) in product.tags" :key="tag" :class="getTagClass(index)">
                <img src="../assets/img/tag-01.svg" class="tags__icon" alt="icon" />{{ tag }}
              </span>
              <span class="downloads">
                <img src="../assets/img/union.svg" class="tags__icon" alt="icon" />{{
                  product.downloads
                }}
              </span>
              <img src="../assets/img/Group 539.png" class="star" alt="star" />
              <img v-if="product.isHot" src="../assets/img/sticker hot.png" class="hot" alt="hot" />
              <img v-if="product.isNew" src="../assets/img/sticker new.png" class="new" alt="new" />
            </div>
            <img :src="`./src/assets/img/${product.image}`" alt="mod pic" />
            <p>{{ product.name }}</p>
          </div>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      products: []
    }
  },
   methods: {
    getTagClass(index) {
      const classes = ['subs', 'sky', 'textures'];
      return classes[index % classes.length];
    },
  },
  async created() {
    try {
      const response = await axios.get('/products.json')
      this.products = response.data
    } catch (error) {
      console.error(error)
    }
  }
}
</script>
