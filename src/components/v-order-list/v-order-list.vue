<template>
    <v-row class="v-order-list">
      <v-col v-if="Number(this.windowWidht) > 1036">
        <v-order-list-item
          :key="i"
          v-for="(item, i) in getDataFromAPI"
          :incomingData="item"/>
      </v-col>
      <v-col v-if="Number(this.windowWidht) <= 1036">
        <vOrderList1024
          :key="i"
          v-for="(item, i) in getDataFromAPI"
          :incomingData="item"/>
      </v-col>
    </v-row>
</template>

<script>
import vOrderListItem from './v-order-list-item'
import vOrderList1024 from './v-order-list-item-1024'
export default {
  name: 'v-order-list',
  components: {
    vOrderListItem,
    vOrderList1024
  },
  mounted () {
    this.windowWidht = window.innerWidth
    window.addEventListener('resize', () => {
      this.windowWidht = window.innerWidth
    })
  },
  data: () => ({
    windowWidht: 0,
    getDataFromAPI: [
      {
        cancel: false,
        applicationDate: '12.05.2021',
        departureData: '12.05.2021',
        status: 'В работе',
        statusEn: 'inWork',
        airport: '(SVO) Шереметьево, Терминал D',
        direction: 'прилет',
        distEn: 'takeOff',
        flightNumber: 'SU347',
        amount: 120000,
        passengers: 'Христофор Колумб, Христофор Колумб Младший',
        contact: 'Христофор Колумб',
        phone: '+7 (989) 747-33-11 ',
        mainService: 'Vip-Зал',
        addService: 'нет',
        addInfo: 'нет'
      },
      {
        cancel: true,
        applicationDate: '12.05.2021',
        departureData: '12.07.2021',
        status: 'отменена',
        statusEn: 'cancel',
        airport: '(BCN) Эль-Прат-де-Льобрегат',
        direction: 'вылет',
        distEn: 'landing',
        flightNumber: 'SU347',
        amount: 120000,
        passengers: 'Христофор Колумб, Христофор Колумб Младший',
        contact: 'Христофор Колумб',
        phone: '+7 (989) 747-33-11 ',
        mainService: 'Vip-Зал',
        addService: 'нет',
        addInfo: 'нет'
      },
      {
        cancel: false,
        applicationDate: '12.05.2021',
        departureData: '12.05.2021',
        status: 'подтверждена',
        statusEn: 'confirmed',
        airport: '(SVO) Шереметьево, Терминал D',
        direction: 'вылет',
        distEn: 'landing',
        flightNumber: 'SU347',
        amount: 120000,
        passengers: 'Христофор Колумб, Христофор Колумб Младший',
        contact: 'Христофор Колумб',
        phone: '+7 (989) 747-33-11 ',
        mainService: 'Vip-Зал',
        addService: 'нет',
        addInfo: 'нет'
      },
      {
        cancel: false,
        applicationDate: '12.05.2021',
        departureData: '12.05.2021',
        status: 'Выполнена',
        statusEn: 'complected',
        airport: '(SVO) Шереметьево, Терминал D',
        direction: 'транзит',
        distEn: 'transit',
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
    margin: 30px auto  auto;
  }
</style>
