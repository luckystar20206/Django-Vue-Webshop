<template>
    <div class="page-product">
        <div class="columns is-multiline">
            <div class="column is-5">
                <figure class="image">
                    <p>
                    <img v-bind:src="product.get_thumbnail" >
                    </p>
                </figure>

            </div>

            <div class="column is-2"></div>

            <div class="column is-5">
                <h1 class="title">{{ product.name }}</h1>
                <h2 class="subtitle">Information</h2>
                <p>{{ product.description }}</p>


                

                <div class="field has-addons mt-6">
                    <div class="control">
                        <input type="number" class="input" min="1" v-model="quantity">
                    </div>

                    <div class="control">
                        <a class="button is-dark" @click="addToCart"> Add to cart</a>
                        
                    </div>
                </div>
                
                <p><strong>Price: </strong>${{ product.price }}</p>
                
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import { toast } from 'bulma-toast'

export default {
    name: 'Product',
    data() {
        return {
            product: {},
            quantity: 1
        }
    },
    mounted() {
        this.getProduct() 
        
    },
    methods: {
        async getProduct() {
            
            this.$store.commit('setIsLoading', true)

            const category_slug = this.$route.params.category_slug
            const product_slug = this.$route.params.product_slug
            await axios
                .get(`/api/v1/products/${category_slug}/${product_slug}`)
                .then(response => {
                    this.product = response.data

                    document.title = this.product.name + ' | Chef-in-the-Box'
                })
                .catch(error => {
                    console.log(error)
                })

            this.$store.commit('setIsLoading', false)
        },
        addToCart() {
            if (isNaN(this.quantity) || this.quantity < 1) {
                this.quantity = 1
            }
            
            const item = {
                product: this.product,
                quantity: this.quantity
            }

            this.$store.commit('addToCart', item)
            
            toast({
                message: 'The product was added to the cart',
                type: 'is-success',
                dismissible: true,
                pauseOnHover: true,
                duration: 3000,
                position: 'bottom-right',
            })
        }
    }
}
</script>    