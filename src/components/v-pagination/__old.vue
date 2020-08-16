<template>
    <v-row class="v-my-pagination text-center justify-center">
      <v-col cols="11">
       <paginate class="d-flex justify-center"
            v-model="byPage"
            :page-count="27"
            :margin-pages="1"
            :page-range="3"
            :prev-text="myPrev"
            :next-text="myNext"
            :container-class="'v-table__pagination'"
            :page-class="'page-item'"
            :page-link-class="'page-link-item'"
            :prev-class="'prev-item'"
            :prev-link-class="'prev-link-item'"
            :next-class="'next-item'"
            :next-link-class="'next-link-item'"
            :break-view-class="'break-view'"
            :break-view-link-class="'break-view-link'"
            :first-last-button="false"
                 :no-li-surround="true"
          ></paginate>
       </v-col>
    </v-row>
</template>

<script>
import Vue from 'vue'
import Paginate from 'vuejs-paginate'
Vue.component('paginate', Paginate)
export default {
  name: 'v-pagination',
  data () {
    return {
      byPage: 1,
      myPrev: '<i class="zmdi zmdi-chevron-left  icon-pagination"></i>',
      myNext: '<i class="zmdi zmdi-chevron-right  icon-pagination"></i>'
    }
  },
  computed: {

  },
  methods: {
  }
}
</script>

<style lang="scss">
  ul {
    list-style-type: none;
  }
  .pagination {
    display: inline-block;
    padding-left: 0;
    margin: 20px 0;
    border-radius: 4px;
   }

  .page-link-item {
    margin: 0 10px;
    width: 44px;
    height: 44px;
    border-radius: 5px;
    align-content: center !important;
    border: 1px solid #DCE1E7;
    color: #0063C3 !important;
      font-family: 'Montserrat', sans-serif;
      font-style: normal;
      font-weight: 500;
      font-size: 20px;
      line-height: 44px;
      text-decoration: none;
  }
  .page-link-item:hover {
    height: 44px;
    color: #FFFFFF !important;
    background: #0063C3;
    box-sizing: border-box;
    border-radius: 5px;
  }
  .active{
    color: #ffffff !important;
    background: #0063C3;
    box-sizing: border-box;
    border-radius: 5px;
  }
  .v-application ul, .v-application ol {
    padding-left: 0;
  }
 .prev-item {
       padding-top: 8px;
    text-align: center;
    width: 44px;
    height: 44px;
    background: #FFFFFF;
    border: 1px solid #DCE1E7;
    box-sizing: border-box;
    border-radius: 5px;
  }
  .prev-link-item {
    margin: 0 20px 0 0;
    padding-top: 8px;
    text-align: center;
    width: 44px;
    height: 44px;
    background: #FFFFFF;
    border: 1px solid #DCE1E7;
    box-sizing: border-box;
    border-radius: 5px;
  }
  .next-item {
    padding-top: 8px;
    text-align: center;
    width: 44px;
    height: 44px;
    background: #FFFFFF;
    border: 1px solid #DCE1E7;
    box-sizing: border-box;
    border-radius: 5px;
  }
  .next-link-item {
    margin: 0 0 0 20px;
    padding-top: 8px;
    text-align: center;
    width: 44px;
    height: 44px;
    background: #FFFFFF;
    border: 1px solid #DCE1E7;
    box-sizing: border-box;
    border-radius: 5px;
  }
  .break-view {
  }
  .break-view-item {
  }

  .v-my-pagination{
    margin: 30px auto 0  auto;
  }

  .icon-pagination{
    color: #0063C3;
    font-weight: 500;
    font-size: 30px !important;
    line-height: 28px !important;
  }
  @media only screen and (max-width: 1366px) {
  .v-my-pagination {
    margin: 0px auto 0 auto;
  }}

</style>
