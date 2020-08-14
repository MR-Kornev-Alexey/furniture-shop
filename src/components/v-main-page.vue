<template>
  <v-container class="v-main-page">
    <v-nav-bar/>
    <v-choice/>
    <v-order-list/>
    </v-container>
</template>
<script>
import vNavBar from '../components/v-nav-bar/v-nav-bar'
import vChoice from '../components/v-choice/v-choice'
import vOrderList from '../components/v-order-list/v-order-list'
export default {
  name: 'v-main-page',
  components: {
    vNavBar,
    vChoice,
    vOrderList
  },
  data: () => ({

  })
}
</script>
