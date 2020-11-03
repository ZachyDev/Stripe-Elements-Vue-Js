<template>
<stripe-checkout ref="checkoutRef" :pk="publishableKey" :items="items" :successUrl="successUrl" :cancelUrl="cancelUrl">
    <template slot="checkout-button">
        <button @click="checkout">Shut up and take my money!</button>
    </template>
</stripe-checkout>
</template>

<script>
import {
    StripeCheckout
} from 'vue-stripe-checkout';
export default {
    components: {
        StripeCheckout
    },
    data: () => ({
        loading: false,
        publishableKey: "pk_test_51HjMvBAKC7vfWzcLuhviBABBa61jqs3XzVqRM9Uc6wWZ20sL21gXkpC77Nnum3J7muJ1CVWW9S9SenE6APXwfPfX00ricpXErF",
        items: [{
            sku: 'sku_FdQKocNoVzznpJ',
            quantity: 1
        }],
        successUrl: 'https://codewithzachy.netlify.com',
        cancelUrl: 'https://rekodi.netlify.app',
    }),
    methods: {
        checkout() {
            this.$refs.checkoutRef.redirectToCheckout();
        }
    }
}
</script>
