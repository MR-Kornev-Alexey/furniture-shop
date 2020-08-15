<template>
  <div class="v-order-list-item">
    <div class="d-flex">
      <div class="block-292 d-flex ">
        <div class="align-self-center padding-left-23 ">Дата подачи заявки:</div>
        <div class="align-self-center padding-left-10 "><span>{{incomingData.applicationDate}}</span></div>
      </div>
      <div class="block-292 d-flex ">
        <div class="align-self-center padding-left-35 ">Дата вылета:</div>
        <div class="align-self-center padding-left-10"><span>{{incomingData.departureData}}</span></div>
      </div>
      <div class="block-292 d-flex ">
        <div class="align-self-center padding-left-23">Статус:</div>
        <span :class="[{'selected-inWork': incomingData.statusEn === 'inWork'},
                       {'selected-cancel': incomingData.statusEn === 'cancel'},
                       {'selected-confirmed': incomingData.statusEn === 'confirmed'},
                       {'selected-complected': incomingData.statusEn === 'complected'}
        ]"
              class="align-self-center padding-left-10">{{incomingData.status}}</span></div>
      <div class="block-292 d-flex padding-left-80 "><span class="align-self-center">подробнее</span>
        <div class="blue-icon align-self-center padding-left-14">
          <img alt="Сортировка" src="../../assets/img/vip-avia/sort.svg">
        </div>
      </div>
    </div>
    <div class="d-flex ">
      <div class="block-584 d-flex">
        <div class="align-self-center padding-left-23">
          <div :class="[{'img-take-of': incomingData.distEn === 'takeOff'},
                         {'img-landing': incomingData.distEn === 'landing'},
                         {'img-transit': incomingData.distEn === 'transit'},
                       ]"></div>
        </div>
        <div class="align-self-center padding-left-12">Аэропорт:</div>
        <span class="align-self-center padding-left-10">{{incomingData.airport}}</span></div>
      <div class="block-292 d-flex">
        <div class="align-self-center padding-left-23">Сумма:</div>
        <div class="align-self-center padding-left-12"><span>{{incomingData.amount}} рублей </span></div>
      </div>
      <div class="block-292 d-flex">
        <div class="align-self-center red-600 padding-left-90"> скачать</div>
        <div class="align-self-center padding-left-14"><img alt="PDF" src="../../assets/img/vip-avia/pdf.svg"></div>
      </div>
    </div>
    <div class="d-flex" v-if="!incomingData.cancel">
      <div class="block-292 d-flex">
        <div class="align-self-center padding-left-23">
          <div :class="[{'img-take-of': incomingData.distEn === 'takeOff'},
                         {'img-landing': incomingData.distEn === 'landing'},
                         {'img-transit': incomingData.distEn === 'transit'},
                       ]"></div>
        </div>
        <div class="align-self-center padding-left-12">Направление:</div>
        <span class="color-status align-self-center padding-left-10">{{incomingData.direction}}</span></div>
      <div class="block-292 d-flex">
        <div class="align-self-center padding-left-35">Номер рейса:</div>
        <div class="align-self-center padding-left-10"><span>{{incomingData.flightNumber}}</span></div>
      </div>
      <div class="block-584 d-flex">
        <div class="align-self-center padding-left-23"> Пассажиры</div>
        <div class="align-self-center padding-left-14"><span>{{incomingData.passengers}}</span></div>
      </div>
    </div>
    <div class="d-flex " v-if="!incomingData.cancel">
      <div class="block-584 d-flex">
        <div class="align-self-center padding-left-23">
          <div :class="[{'img-take-of': incomingData.distEn === 'takeOff'},
                         {'img-landing': incomingData.distEn === 'landing'},
                         {'img-transit': incomingData.distEn === 'transit'},
                       ]"></div>
        </div>
        <div class="align-self-center padding-left-12">Основная услуга:</div>
        <span class="color-status align-self-center padding-left-10">{{incomingData.mainService}}</span></div>
      <div class="block-584 d-flex">
        <div class="align-self-center padding-left-23"> Контактное лицо</div>
        <div class="align-self-center padding-left-14"><span>{{incomingData.contact}}</span></div>
      </div>
    </div>
    <div class="d-flex " v-if="!incomingData.cancel">
      <div class="block-584 d-flex">
        <div class="align-self-center padding-left-23">
          <div :class="[{'img-take-of': incomingData.distEn === 'takeOff'},
                         {'img-landing': incomingData.distEn === 'landing'},
                         {'img-transit': incomingData.distEn === 'transit'},
                       ]"></div>
        </div>
        <div class="align-self-center padding-left-12">Доп услуги:</div>
        <span class="color-status align-self-center padding-left-16">{{incomingData.addService}}</span></div>
      <div class="block-584 d-flex">
        <div class="align-self-center padding-left-23"> Контактный телефон</div>
        <div class="align-self-center padding-left-14"><span>{{incomingData.phone}}</span></div>
      </div>
    </div>
    <div class="d-flex " v-if="!incomingData.cancel">
      <div class="block-1170 d-flex">
        <div class="align-self-center padding-left-23">Доп. информация:</div>
        <span class="color-status align-self-center padding-left-6">{{incomingData.addInfo}}</span></div>
    </div>
    <div class="d-flex ">
      <div class=" d-flex justify-center repeat-order">
        <div class="align-self-center "><span>Повторить заказ</span> <i class="zmdi zmdi-repeat icon-gray"></i></div>
      </div>
      <div class=" d-flex justify-center edit-order">
        <div class="align-self-center "><span>Запросить редактирование </span><i
          class="zmdi zmdi-mail-reply icon-gray"></i></div>
      </div>
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

    ]
  })
}
</script>

<style lang="scss">
  .v-order-list-item {
    max-width: 1170px;
    margin: 0 auto 34px auto;
    font-family: SF UI Display;
    font-style: normal;
    font-weight: normal;
    font-size: 16px;
    line-height: 135%;
    /* identical to box height, or 22px */
    color: #777777;

    span {
      color: #333333;
      font-size: 16px;
      line-height: 135%;
    }

    .repeat-order {
      background: #E7E7E7;
      border-radius: 0 0 0 4px;
      cursor: pointer;
      width: 584px;
      height: 44px;
    }

    .edit-order {
      background: #C1FBFF;
      border-radius: 0 0 4px 0;
      cursor: pointer;
      width: 584px;
      height: 44px;
    }

    .red-600 {
      font-weight: 600;
      font-size: 16px;
      line-height: 135%;
      /* identical to box height, or 22px */
      color: #DA5E52;
    }

    .blue-icon {
      font-weight: 500;
      font-size: 18px;
      line-height: 20px;
      /* identical to box height */
      text-align: center;
      color: #007BFF;
    }

    .theme--light.v-icon {
      color: #007BFF;
    }
  }

  .v-icon.v-icon {
    font-size: 18px;
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

  .block-1170 {
    width: 1170px;
    height: 44px;
    border: 1px solid #DCE1E7;
  }

  .selected-inWork {
    color: #30C2FF !important;
  }

  .selected-cancel {
    color: #DA5E52 !important;
  }

  .selected-confirmed {
    color: #0BAC11 !important;
  }

  .selected-complected {
    color: #007BFF !important;
  }

  .img-take-of {
    background-image: url("../../assets/img/vip-avia/take-of.svg");
    background-repeat: no-repeat;
    background-size: cover;
    height: 26px;
    width: 26px;
  }
  .img-landing {
    background-image: url("../../assets/img/vip-avia/landing.svg");
    background-repeat: no-repeat;
    background-size: cover;
    height: 26px;
    width: 26px;
  }
  .img-transit {
    background-image: url("../../assets/img/vip-avia/transit.svg");
    background-repeat: no-repeat;
    background-size: cover;
    height: 26px;
    width: 26px;
  }
</style>
