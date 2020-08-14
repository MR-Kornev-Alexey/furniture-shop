<template>
  <div class="v-order-list-item">

  </div>
</template>

<script>
export default {
  name: 'v-order-list-item',
  data: () => ({
    colorStatus: [
      {
        inWork: '#30C2FF',
        canceled: '#DA5E52',
        confirmed: '#0BAC11',
        completed: '#007BFF'
      }

    ],
    options: [
      {
        applicationDate: '12.05.2021',
        departureData: '12.05.2021',
        status: 'В работе',
        statusEn: 'inWork',
        airport: '(SVO) Шереметьево, Терминал D',
        direction: 'прилет',
        flightNumber: 'SU347',
        amount: 120000,
        passengers: 'Христофор Колумб Младший, Христофор Колумб Младший',
        contact: 'Христофор Колумб',
        phone: '+7 (989) 747-33-11 '
      }
    ]
  })
}
</script>

<style scoped>

</style>
