<template>
  <div class="home">
    <section class="hero is-medium is-dark mb-6">
        <div class="hero-body has-text-centered">
            <p class="title mb-6">
                Welcome to Chef-in-the-Box
            </p>
            <p class="subtitle">
                The little chef in your kitchen
            </p>
        </div>
    </section>

    <div class="columns is-multiline">
      <div class="column is-12">
          <h2 class="is-size-2 has-text-centered">Latest products</h2>
      </div>

      <ProductComponent 
        v-for="product in latestProducts"
        v-bind:key="product.id"
        v-bind:product="product" />
    </div>
  </div>
</template>

<script>
import axios from 'axios'

import ProductComponent from '@/components/ProductComponent'


export default {
  data() {
    return {
      latestProducts: []
    }
  },
  components: {
    ProductComponent
  },
  mounted() {
    this.getLatestProducts()

    document.title = 'Home | Chef-in-the-Box'
  },
  methods: {
    
    async getLatestProducts() {
      this.$store.commit('setIsLoading', true)

      await axios
      .get('/api/v1/latest-products/')
      .then(response => {
        this.latestProducts = response.data
      })
      .catch(error => {
        console.log(error)
      })

      this.$store.commit('setIsLoading', false)
    }
  }
}
</script>