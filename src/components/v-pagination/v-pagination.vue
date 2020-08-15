<template>
    <v-row class="v-my-pagination text-center justify-center">
      <v-col cols="11">
        <div class="v-table__pagination ">
          <div class="page-table-left align-self-center"><i class="zmdi zmdi-chevron-left  icon-pagination"></i>
          </div>
          <div class="page d-flex justify-center"
               v-for="page in pages"
               :key="page"
               :class="{'link-page__selected': page === pageNumber}"
               @click="pageClick(page)"
          > <div class="align-self-center justify-center">{{page}}</div>
          </div>
          <div class="page-table-right align-self-center"><i class="zmdi zmdi-chevron-right  icon-pagination"></i>
          </div>
        </div>
      </v-col>
    </v-row>
</template>

<script>

export default {
  name: 'v-pagination',
  data () {
    return {
      linksPerPage: 10,
      pageNumber: 1,
      allPages: 56,
      byPage: 1
    }
  },
  computed: {
    pages () {
      const num = Math.ceil(parseInt(this.allPages) / 10)
      return num > 0 ? num : 1
    }
  },
  methods: {
    pageClick (page) {
      this.pageNumber = page
    }
  }
}
</script>

<style lang="scss">
  .v-my-pagination{
    margin: 0 auto 0  auto;
  }
  .v-table__pagination{
    display: inline-flex;
    .page{
      width: 44px;
      height: 44px;
      border-radius: 5px;
      margin: 0 4px;
      cursor: pointer;
      font-family: 'Montserrat', sans-serif;
      font-style: normal;
      font-weight: 500;
      font-size: 20px;
      line-height: 24px;
      color: #0063C3;
     }
  }
  .page:hover {
    background: #FFFFFF;
    border: 1px solid #DCE1E7;
    box-sizing: border-box;
    border-radius: 5px;
  }
  .link-page__selected {
    background: #0063C3;
    color: #ffffff !important;
  }
  .icon-pagination{
    color: #0063C3;
    font-weight: 500;
    font-size: 40px !important;
    line-height: 28px !important;
  }
  .page-table-left{
    margin: 0  10px;
  }
  .page-table-right{
    margin: 0 10px ;
  }
</style>
