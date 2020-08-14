<template>
  <div
    class="overflow-hidden nav-main"
  >
    <v-app-bar
      color="white"
      light
    >
      <v-app-bar-nav-icon @click="drawer = true" v-if="$vuetify.breakpoint.smAndDown"></v-app-bar-nav-icon>
      <v-row class="d-flex ">
        <v-col class="main-nav" cols="12" v-if="!$vuetify.breakpoint.smAndDown">
          <div class="d-flex main-nav__top">
            <div class="d-flex main-nav__top__color">
              <div :class="[
              { 'margin-left-0 d-flex align-self-center font14': item.font14&&item.left0},
              { 'margin-left-30 d-flex align-self-center font14': item.font14&&item.left30},
              { 'margin-left-30 d-flex align-self-center font11': item.font11&&item.left30},
              { 'margin-left-27 d-flex align-self-center font11': item.font11&&item.left27},
              { 'margin-left-15 d-flex align-self-center': item.left15},
              { 'margin-left-60 d-flex align-self-center': item.left60},
                                    ]"
                   :key="i"
                   v-for="(item, i) in mainMenu">
                <img :alt="item.alt" :class="[
              { 'margin-right-6': item.pic6},
               { 'margin-right-12': item.pic12}
                                    ]"
                     :src="item.src"
                >
                <a :href="item.href">{{item.name}}</a>

              </div>
            </div>

          </div>

          <div class="d-flex sub-nav ">
            <div class="d-flex sub-nav__menu">
              <div class="d-flex logo-block">
                <img src="../../assets/img/vip-avia/logo_image.svg" alt="Logo">
                <div>
                  <div class="logo-block__tittle">VIP <span>AVIA</span></div>
                  <div>SERVICE</div>
                </div>
              </div>
              <div :class="[
              { 'margin-left-33 selected d-flex align-self-center': item.selected&&item.left33 },
               { 'margin-left-31 selected d-flex align-self-center': item.selected&&item.left31 },
              { 'margin-left-15 selected d-flex align-self-center': item.selected&&item.left15 },
              { 'margin-left-19 selected d-flex align-self-center': item.selected&&item.left19},
                 { 'margin-left-33 d-flex align-self-center': !item.selected&&item.left33 },
               { 'margin-left-31  d-flex align-self-center': !item.selected&&item.left31 },
              { 'margin-left-15  d-flex align-self-center': !item.selected&&item.left15 },
              { 'margin-left-19 d-flex align-self-center': !item.selected&&item.left19}
            ]"
                   :key="i"
                   v-for="(item, i) in subMenu"
              >
                <a :href="item.href">{{item.name}}</a>
              </div>
              <div>
                <button class="orange-button margin-left-33 ">Заказать</button>
              </div>
              <div>
                <button class="button-44 margin-left-15 "><i class="zmdi zmdi-search icon-gray"></i></button>
              </div>
              <div>
                <button class="button-71 margin-left-15 "><i class="zmdi zmdi-brightness-3 icon-gray"></i> <i class="icon-pale">|</i><i class="zmdi zmdi-sun icon-orange"></i></button>
              </div>
              <div class="main-shop"  >
                <button class="button-44 margin-left-15 "><i class="zmdi zmdi-shopping-cart icon-gray"></i></button>
                <div class="shop-round">2</div>
              </div>
              <div>
                <button class="button-44 margin-left-15 "> <i class="zmdi zmdi-account icon-gray"></i></button>
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
          class="side-sub-menu"
          v-model="group"
        >
          <v-list-item :key="i"
                       v-for="(item, i) in subMenu"
          >
            <v-list-item-title>{{item.name}}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: 'v-nav-bar',
  data: () => {
    return ({
      group: '',
      drawer: false,
      mainMenu: [
        {
          left0: true,
          name: '8 (800) 333-17-85 ',
          src: require('../../assets/img/vip-avia/smartphone-iphone.svg'),
          alt: 'Cellphone',
          pic6: true,
          font14: true,
          href: '#'
        },
        {
          left30: true,
          name: '+7 (495) 120-57-55',
          src: require('../../assets/img/vip-avia/smartphone-iphone.svg'),
          alt: 'Cellphone',
          pic6: true,
          font14: true,
          href: '#'
        },
        {
          left30: true,
          name: 'Корпоративным клиентам',
          src: require('../../assets/img/vip-avia/info-outline.svg'),
          alt: 'Info',
          pic12: true,
          font11: true,
          href: '#'
        },
        {
          left27: true,
          name: 'Турагенствам',
          font11: true,
          href: '#'
        },
        {
          left27: true,
          name: 'Личным помощникам',
          font11: true,
          href: '#'
        },
        {
          left27: true,
          name: 'Частным клиентам',
          font11: true,
          href: '#'
        },
        {
          left60: true,
          src: require('../../assets/img/vip-avia/visa_icon.svg'),
          alt: 'Info'
        },
        {
          left15: true,
          src: require('../../assets/img/vip-avia/master_card_icon.svg'),
          alt: 'Info'
        }

      ],
      subMenu: [
        {
          left33: true,
          name: 'Услуги',
          selected: false,
          href: '#'
        },
        {
          left19: true,
          name: 'Аэропорты',
          selected: false,
          href: '#'
        },
        {
          left19: true,
          name: 'Калькулятор',
          selected: false,
          href: '#'
        },
        {
          left19: true,
          name: 'О компании',
          selected: true,
          href: '#'
        },
        {
          left19: true,
          name: 'Блог',
          selected: false,
          href: '#'
        },
        {
          left19: true,
          name: 'Контакты',
          selected: false,
          href: '#'
        }
      ]
    }
    )
  }
}
</script>

<style lang="scss" scoped>
  .side-sub-menu {
    text-transform: uppercase;
    background-color: #DADADA;
  }

  .nav-main {
    margin: 0 auto 0 auto;
    padding: 8px 0 0 0;
     }

  .img-logo {
    padding-bottom: 6px;
    margin: 0 -254px 0 0;
  }

  .main-nav {
    .main-nav__top{
        padding: 0 0 0 374px;
        margin: 0 0 14.5px 0;
    }
    .main-nav__top {
      min-height: 44px;
      font-family: 'Montserrat', sans-serif;
      background: #142D50;

      font-style: normal;
      font-weight: bold;
      text-transform: uppercase;
      a{
        color: #FFFFFF;
        text-decoration: none;
      }
      a:hover{
        color: #9e9e9e;
        transition-duration: 500ms;
      }
    }
  }

  .sub-nav {

    .main-shop{
      position: relative;
      .shop-round{
        text-align: center;
        position: absolute;
        bottom: -8px;
        left: 7px;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        background: #FF6A28;
        color: #FFFFFF;
      }
    }
  .selected a{
      color: #007BFF !important;
    }
    .selected a:hover{
      color: #9bc9fb !important;
    }
     margin: 5px 0 -26.5px 0;
      padding: 0 0 0 374px;
    .logo-block{
      margin: 4px 0 0 0;
      font-weight: 600;
      font-size: 14px;
      letter-spacing: 2.5px;
      img{
        margin: 0 10px 0 0;
      }
      .logo-block__tittle{

        span{
          margin: 0 0 0 -6px;
          font-style: normal;
          font-weight: 800;
          font-size: 16px;
          line-height: 20px;
          letter-spacing: 0.1em;
          text-transform: uppercase;
          color: #FF6A28;
        }
      }
    }
    .sub-nav__menu a {
      font-style: normal;
      font-weight: 500;
      font-size: 14px;
      line-height: 17px;
      letter-spacing: 1.2px;
      color: #333333;
      text-transform: uppercase;
      text-decoration: none;
    }
    .sub-nav__menu a:hover{
      color: #9e9e9e;
      transition-duration: 500ms;
    }

  }

  .font14 {
    font-size: 14px;
    line-height: 28px;
  }

  .font11 {
    font-size: 11px;
    line-height: 18px;
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

  @media only screen and (max-width: 1140px) {
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
    .margin-left-40, .margin-left-48 {
      margin: 0 0 0 23px;
      padding: 0 0 0 0;
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
    .sub-nav {
      align-self: end;
    }
  }

  @media only screen and (max-width: 900px) {
    .img-logo {
      margin: 0 0 0 -16px;
    }
    .v-btn--icon.v-size--default .v-icon {
      font-size: 32px;
    }
  }

  @media only screen and (max-width: 768px) {
    .img-logo {
      margin: 0 0 0 -16px;
    }
    .v-btn--icon.v-size--default .v-icon {
      font-size: 32px;
    }
  }
</style>
