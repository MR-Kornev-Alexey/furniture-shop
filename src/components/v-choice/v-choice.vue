<template>
  <v-row class="">
    <div class="first-block">
      <v-my-select :options="options" class="v-select-bar" label="title">
        <template slot="option" slot-scope="option">
          <div>
            <span :class="option.icon" class="zmdi icon-gray"></span>
            <span class="v-select-out">{{ option.title }}</span>
          </div>
        </template>
      </v-my-select>
    </div>
    <div class="second-block">
      <v-my-select :options="dataFilter" class="v-select-bar" label="title">
        <template slot="option" slot-scope="option">
          <div>
            <span :class="option.icon" class="zmdi icon-gray"></span>
            <span class="v-select-out">{{ option.title }}</span>
          </div>
        </template>
      </v-my-select>
    </div>
    <div class="upload-block">
      <div class="v-select-bar-csv d-flex justify-center">
        <div class="d-flex align-self-center">Скачать все в CSV <i class="zmdi zmdi-file-text" style="margin: 0 0 0 9px; font-size: 24px"></i></div>

      </div>
    </div>
  </v-row>
</template>

<script>
import Vue from 'vue'
import vSelect from 'vue-select'
import 'vue-select/dist/vue-select.css'

Vue.component('v-my-select', vSelect)
export default {
  name: 'v-choice',
  data: () => ({
    options: [
      {
        title: 'Корзина',
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
    ],
    dataFilter: [
      {
        title: 'По дате оформления',
        icon: 'zmdi-sort-asc',
        url: 'https://codeclimate.com/github/sagalbot/vue-select'
      },
      {
        title: 'По другой дате',
        icon: 'zmdi-sort-asc',
        url: 'https://codeclimate.com/github/sagalbot/vue-select'
      },
      {
        title: 'По еще одной дате',
        icon: 'zmdi-sort-asc',
        url: 'https://codeclimate.com/github/sagalbot/vue-select'
      }
    ]
  })
}
</script>

<style lang="scss">
  .first-block {
    margin: 0 0 0 374px;
    padding: 6px 0 0 0;
  }

  .second-block {
    margin: 0 0 0 32px;
    padding: 6px 0 0 0;
  }

  .upload-block, {
    margin: 0 0 0 30px;
    padding: 6px 0 0 0;
  }

  .v-select-out {
    margin-left: 20px;
  }

  .v-select-out, .vs__selected {
    text-align: right;
    font-style: normal;
    font-weight: normal;
    font-size: 20px;
    line-height: 135%;
    color: #777777;
  }

  .vs__selected-options {
    width: 344px;
    height: 47px;
    justify-content: right;
  }

  .v-select-bar {
    box-sizing: border-box;
    border-radius: 5px;
  }

  .v-select-bar-csv {
    width: 370px;
    height: 50px;
    background: #FFFFFF;
    border: 1px solid #207245;
    box-sizing: border-box;
    border-radius: 5px;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 135%;
    /* identical to box height, or 27px */
    color: #207245;
  }
</style>
