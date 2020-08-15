<template>
    <v-row class="v-order-list">
      <v-col>
        <v-order-list-item
          :key="i"
          v-for="(item, i) in getDataFromAPI"
          :incomingData="item"/>
      </v-col>
    </v-row>
</template>

<script>
import vOrderListItem from './v-order-list-item'
export default {
  name: 'v-order-list',
  components: {
    vOrderListItem
  },
  data: () => ({
    getDataFromAPI: [
      {
        applicationDate: '12.05.2021',
        departureData: '12.05.2021',
        status: 'В работе',
        statusEn: 'inWork',
        airport: '(SVO) Шереметьево, Терминал D',
        direction: 'прилет',
        flightNumber: 'SU347',
        amount: 120000,
        passengers: 'Христофор Колумб, Христофор Колумб Младший',
        contact: 'Христофор Колумб',
        phone: '+7 (989) 747-33-11 ',
        mainService: 'Vip-Зал',
        addService: 'нет',
        addInfo: 'нет'
      }
    ]
  })
}
</script>

<style lang="scss">
  .v-order-list{
    margin: 30px auto 0 auto;
  }
</style>
