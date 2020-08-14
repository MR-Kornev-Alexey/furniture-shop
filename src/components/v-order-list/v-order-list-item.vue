<template>
  <div class="v-order-list-item">
    <div class="d-flex">
      <div class="block-292">Дата подачи заявки:{{incomingData.applicationDate}}</div>
      <div class="block-292">Дата вылета:{{incomingData.departureData}}</div>
      <div class="block-292">Статус: {{incomingData.status}}</div>
      <div class="block-292"> подробнее</div>
    </div>
    <div class="d-flex">
      <div class="block-584">Аэропорт:{{incomingData.airport}}</div>
      <div class="block-292">Сумма:{{incomingData.amount}} рублей</div>
      <div class="block-292">Статус: {{incomingData.status}}</div>
      <div class="block-292"> Скачать</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'v-order-list-item',
  props: ['incomingData'],
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
  .v-order-list-item {
    max-width: 1170px;
    margin: 0 auto 0 auto;

  }

  .block-292 {
    width: 292px;
    height: 44px;
    border: 1px solid #DCE1E7;
  }

  .block-584 {
    width: 584px;
    height: 44px;
    border: 1px solid #DCE1E7;
  }

</style>
