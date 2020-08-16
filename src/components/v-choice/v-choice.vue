<template>
  <v-row class="v-choice d-flex justify-center">
    <div class="first-block">
      <label>
        <select>
          <option> &#xf07a; Корзина </option>
          <option> &#xf07a; Корзина-1 </option>
          <option> &#xf15d; Корзина-2 </option>
        </select>
      </label>
      <v-my-select :options="options" class="v-select-bar" label="title" >
        <template  slot="option" slot-scope="option">
          <div>
            <span :class="option.icon" class="zmdi icon-gray"></span>
            <span class="v-select-out">{{ option.title }}</span>
          </div>
        </template>
      </v-my-select>
    </div>
    <div class="second-block">
      <label>
        <select>
          <option> &#xf15d; По дате оформления </option>
          <option> &#xf15d; По другой дате  </option>
          <option> &#xf15d; И по еще дате </option>
        </select>
      </label>
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
        url: 'https://codeclimate.com/github/sagalbot/vue-select',
        choice: false
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
  .vs__actions{
    width: 47px;
  }
  .first-block {
    margin: 0;
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
    width: 320px;
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
  @media only screen and (max-width: 1366px) {
    .first-block {
          padding: 6px 0 0 0;
    }
  }
  @media only screen and (max-width: 1140px) {
    .vs__selected-options {
      width: 265px;
    }
    }
  @media only screen and (max-width: 1024px){
    .v-select-bar-csv {
      width: 281px;
      height: 50px;
    }
   .vs__selected-options {
     width: 231px;
      }}
</style>
