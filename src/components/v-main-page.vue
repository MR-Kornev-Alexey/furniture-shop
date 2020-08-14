<template>
  <v-container class="v-main-page">
    <v-nav-bar/>
    <v-choice/>
    </v-container>
</template>
<script>
import vNavBar from '../components/v-nav-bar/v-nav-bar'
import vChoice from '../components/v-choice/v-choice'
export default {
  name: 'v-main-page',
  components: {
    vNavBar,
    vChoice
  },
  data: () => ({

  })
}
</script>
