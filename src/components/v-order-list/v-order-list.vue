<template>
    <v-row class="v-order-list">
      <v-col>

      </v-col>
    </v-row>
</template>

<script>
export default {
  name: 'v-order-list',
  data: () => ({
    options: [
      {
        applicationDate: 'Корзина',
        icon: 'zmdi-shopping-cart',
        url: 'https://codeclimate.com/github/sagalbot/vue-select'
      },
      {
        title: 'Корзина -1',
        icon: 'zmdi-shopping-cart',
        url: 'https://codeclimate.com/github/sagalbot/vue-select'
      },
      {
        title: 'Корзина-2',
        icon: 'zmdi-shopping-cart',
        url: 'https://codeclimate.com/github/sagalbot/vue-select'
      }
    ]
  })
}
</script>

<style scoped>

</style>
