<template>
  <div
    class="overflow-hidden nav-main"
  >
    <v-app-bar
      color="white"
      light
    >
      <v-app-bar-nav-icon @click="drawer = true" v-if="$vuetify.breakpoint.smAndDown"></v-app-bar-nav-icon>
      <v-row class="d-flex justify-center">
        <v-col v-if="!$vuetify.breakpoint.smAndDown" class="main-nav" md="10">
          <div class="d-flex main-nav__top">
            <div :class="[
              { 'margin-left-0': item.left0},
              { ' margin-left-48': item.left48},
              { 'margin-left-40': item.left40},
                                    ]"
                 :key="i"
                 v-for="(item, i) in mainMenu">
              {{item.name}}
            </div>
                 </div>

          <div class="d-flex sub-nav ">
            <div class="d-flex sub-nav__menu">
              <div :class="[
              { 'margin-left-0': item.left0 },
              { 'margin-left-50': item.left50 },
              { 'margin-left-62': item.left62}
            ]"
                   :key="i"
                   v-for="(item, i) in subMenu"
              >
                {{item.name}}
              </div>
            </div>
            <div class="nav-icons d-flex">
              <div class="nav-icons__search">
                <img alt="Search" src="../../assets/img/svg/search.svg">
              </div>
              <div class="shopping-bag">
                <img alt="bag" src="../../assets/img/svg/shopping-bag.svg">
                <div class="shopping-bag__round d-flex justify-center align-content-center">
                  <div class="align-self-center">1</div>
                </div>
              </div>

            </div>
          </div>

        </v-col>
      </v-row>
      <div>

      </div>

      <div>

      </div>
    </v-app-bar>

    <v-navigation-drawer
      absolute
      temporary
      v-model="drawer"
    >
      <v-list
        dense
        nav
      >
        <v-list-item-group
          active-class="deep-purple--text text--accent-4"
          v-model="group"
        >
          <v-list-item :key="i"
                       v-for="(item, i) in mainMenu">
            <v-list-item-title>{{item.name}}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
        <v-list-item-group
          active-class="deep-purple--text text--accent-4"
          v-model="group"
          class="side-sub-menu"
        >
          <v-list-item :key="i"
                       v-for="(item, i) in subMenu"
                       >
            <v-list-item-title >{{item.name}}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: 'v-nav-bar',
  data: () => ({
    group: '',
    drawer: false,
    mainMenu: [
      {
        left0: true,
        name: '8 (800) 333-17-85 '
      },
      {
        left30: true,
        name: '+7 (495) 120-57-55'
      },
      {
        left30: true,
        name: 'О производстве'
      },
      {
        left30: true,
        name: 'Корпоративным клиентам'
      },
      {
        left25: true,
        name: 'Турагенствам'
      },
      {
        left25: true,
        name: 'Личным помощникам'
      },
      {
        left25: true,
        name: 'Частным клиентам'
      }
    ],
    subMenu: [
      {
        left0: true,
        name: 'Диваны'
      },
      {
        left62: true,
        name: 'Кровати'
      },
      {
        left50: true,
        name: 'Детская мебель'
      },
      {
        left50: true,
        name: 'Кресла'
      },
      {
        left50: true,
        name: 'Тумбы'
      }
    ]
  })
}
</script>

<style lang="scss" scoped>
  .side-sub-menu{
    text-transform: uppercase;
    background-color: #DADADA;
  }
  .nav-main {
    margin: 0 auto 0 auto;
    height: 127px;
    font-family: 'Montserrat', sans-serif;
  }

  .img-logo {
    padding-bottom: 6px;
    margin: 0 -254px 0 0;
  }

  .main-nav {
    .main-nav__top {
      padding-top: 6px;
     }
  }

  .sub-nav {
    margin-top: 34px;

    .sub-nav__menu {
      margin-top: 10px;
      text-transform: uppercase;
    }
  }

  .margin-left-0 {
    margin-left: 0;
  }

  .margin-left-30 {
    margin-left: 30px;
  }

  .margin-left-25 {
    margin-left: 25px;
  }
.nav-icons {
    .nav-icons__search {
      img {
        height: 19px;
      }
    }
    margin-left: 127px;
    .shopping-bag {
      margin-left: 36px;
      position: relative;

      .shopping-bag__round {
        position: absolute;
        bottom: -4px;
        right: -4px;
        background-color: #FDC94C;
        width: 13px;
        height: 13px;
        border-radius: 50%;

        div {
          font-size: 11px;
        }
      }
    }

  }

  .nav-phone {
    margin-left: 240px;

    .nav-phone__sub {
      font-size: 12px;
      line-height: 14px;
    }
  }

  .nav-phone__num {
    font-family: "Akzidenz-Grotesk Pro", sans-serif;
    font-weight: 500;
    font-size: 15px;
    line-height: 20px;
    letter-spacing: 1px;
    padding-left: 45px;
  }

  @media only screen and (max-width: 1680px) {
    .img-logo {
      margin: 0 -82px 0 0;
    }
    .main-nav {
      padding-left: 146px;
    }
  }

  @media only screen and (max-width: 1600px) {
    .img-logo {
      margin: 0 -38px 0 0;
    }
    .main-nav {
      padding-left: 109px;
    }
  }

  @media only screen and (max-width: 1440px) {
    .img-logo {
      margin: 0 0 0 -76px;
    }
    .main-nav {
      padding-left: 67px;
    }
  }

  @media only screen and (max-width: 1400px) {
    .main-nav {
      padding-left: 84px;
    }
  }

  @media only screen and (max-width: 1366px) {
    .margin-left-40 {
      margin-left: 33px;
    }
    .nav-icons {
      margin-left: 154px;
      margin-top: 4px;
    }
    .nav-phone {
      margin-left: 209px;
    }
  }

  @media only screen and (max-width: 1280px) {
    .nav-phone {
      margin-left: 160px;
    }
    .main-nav {
      padding-left: 51px;
    }
    .margin-left-48 {
      margin-left: 24px;
    }
    .nav-icons .shopping-bag .shopping-bag__round {
      bottom: -2px;
      right: -7px;
    }
  }

  @media only screen and (max-width: 1140px){
     .margin-left-40 {
     margin-left: 24px;
   }
    .nav-phone {
      margin-left: 94px;
    }
  }
  @media only screen and (max-width: 1024px) {
    .main-nav .main-nav__top .main-nav__top_item_short {
      width: 74px;
    }
  .nav-icons {
      margin: 0 -60px 0 -16px;
     }
    .main-nav .main-nav__top .main-nav__top_item_long {
      width: 159px;
    }
    .margin-left-40,.margin-left-48 {
      margin: 0 0 0 23px ;
      padding: 0 0 0 0 ;
    }
    .img-logo {
      margin: 0 0 0 -166px;
    }
    .main-nav {
      padding-left: 26px;
    }
    .nav-phone {
      margin: 0 0 0 16px;
    }
    .sub-nav{
      align-self: end;
    }
  }
  @media only screen and (max-width: 900px) {
    .img-logo{
      margin: 0 0 0 -16px;
    }
    .v-btn--icon.v-size--default .v-icon {
      font-size: 32px;
    }
     }
  @media only screen and (max-width: 768px) {
    .img-logo{
      margin: 0 0 0 -16px;
    }
    .v-btn--icon.v-size--default .v-icon {
            font-size: 32px;
         }
    }
</style>
