<template>
  <v-app>
    <header class="header pc_hyoji">
      <div class="header_inner flexbox">
        <div id="nav-drawer" class="header_inner_head flexbox">
          <v-app-bar
            color="primary"
            :clipped-left="clipped"
            fixed
            app

          >

          <!-- <v-container> -->
<div class="flex-container2">
            <v-toolbar-title id="logo" class="title flexbox">Vuetify</v-toolbar-title>

            <v-list dense class="d-flex">
              <!-- <v-list v-if="$vuetify.breakpoint.mdAndUp" dense class="d-flex ml-8"> -->
<div class="navmenu">
                <v-list-item v-for="menu in menus" :key="menu.title" class="pa-0 flexbox">
                  <v-btn text class="flexbox">
                    <v-icon class ="flexbox">{{ menu.icon }}</v-icon>
                      {{ menu.title }}
                  </v-btn>
                </v-list-item>
</div>
            </v-list>
</div>
          <!-- </v-container> -->

          <v-spacer />

            <nav class="navi auth_buttons flexbox">
              <nuxt-link to="/signin">
                <v-btn

                  text
                  small
                  class="text-caption pa-0"
                >
                  ログイン
                </v-btn>
              </nuxt-link>
              <!-- 登録 -->
              <nuxt-link to="/signup">
                <v-btn

                  text
                  small
                  class="text-caption pa-0"
                >
                  登録
                </v-btn>
              </nuxt-link>

              <v-btn
                v-if="!isLoggedin && $vuetify.breakpoint.xs"
                  text
                  small
                  class="text-caption pa-0"
                icon

              >
                <v-icon>mdi-menu</v-icon>
              </v-btn>


            </nav>
            </v-app-bar>
            <!-- <v-main>
              <v-container>
                <Nuxt />
              </v-container>
            </v-main> -->

            <v-navigation-drawer
              v-model="rightDrawer"
              temporary
              fixed
            >
              <v-list>
                <v-list-item
                  v-for="(item, i) in menuItems"
                  :key="i"
                  :to="item.to"
                  router
                  exact
                >
                  <v-list-item-action>
                    <v-icon>{{ item.icon }}</v-icon>
                  </v-list-item-action>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.title" />
                  </v-list-item-content>
                </v-list-item>
              </v-list>
            </v-navigation-drawer>
        </div>
      </div>
    </header>

    <!--親要素-->
    <div class="flex-container">
    <!--子要素-->
      <div class="flex-item">①</div>
      <div class="flex-item">②</div>
      <div class="flex-item">③</div>
      <div class="flex-item">④</div>
      <div class="flex-item">⑤</div>
      <div class="flex-item">⑥</div>
      <div class="flex-item">⑦</div>
      <div class="flex-item">⑧</div>
      <div class="flex-item">⑨</div>
      <div class="flex-item">⑩</div>
    </div>


    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import constants from '../common/constants.js' // 今回追加
export default {
  data () {
    return {
      menus: [
        { title: 'メンターをさがす', icon: 'mdi-account' },
        { title: 'プランをさがす', icon: 'mdi-laptop-mac' },
        { title: 'イベントを探す', icon: 'mdi-account' },
        { title: 'ナレッジ', icon: 'mdi-laptop-mac' }
      ],
      clipped: false,
      drawer: false,
      fixed: false,
      menuItems: constants.menuItems, // 今回追加
      // items: [
      //   {
      //     icon: 'mdi-apps',
      //     title: 'Welcome',
      //     to: '/'
      //   },
      //   {
      //     icon: 'mdi-chart-bubble',
      //     title: 'Inspire',
      //     to: '/inspire'
      //   }
      // ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>

<style>
header {
  display: block;
  border-style: 10px solid;
  position: sticky;
  padding: 0 4%;
  top: 0;
  background: #fff;
  transition: all .8s;
  z-index: 2;
  position: sticky;
}

@media (max-width: 960px) and (min-width: 699px){
  .pc_hyoji {
    display: block!important;
  }
}
@media (max-width: 960px) and (min-width: 699px){
  header .header_inner{
    margin-right: auto;
    padding: 8px 0;
  }
}

@media (max-width: 960px) and (min-width: 699px){
  header .header_inner #logo{
    background-color: green;
    margin-right: auto;
    padding: 8px 0;
  }
}
/* ここはいる */
header .header_inner #logo{
  margin: 0;
  line-height: 0;
}

header .header_inner .menu {
  font-weight: 600;
  position: relative;
}
/* ここはいる */
header .header_inner .flexbox {
  align-items: center;
}

header .header_inner_head {
  height: 72px;
}
/* @media screen and (max-width: 960px){
  .v-btn__content{
      margin-right: 24px;
  }
} */
.v-btn__content{
  height: 100%;
  align-items: center;
  margin-right: 24px;
  font-size:14px;
}

.v-btn__content .flexbox{
  display: flex;
  flex-wrap: wrap;
}

header .flexbox{
  display: flex;
  flex-wrap: wrap;
}

header .header .pc_hyoji{
  display: block!important;
}

header .flex-container2 #logo{
  margin: 0;
  line-height: 0;
  padding: 8px 40px 8px 0;
}
/* ここの高さが重要 */
header .flex-container2 .title{
  height: 56px;
  align-items: center;
  color: #ff0000;
  border-style: solid;
}

#nav-drawer{
  width: 100%;
  align-items: center;
}

header .header_inner {
  align-items: center;
  height: 72px;
  max-width: 1200px;
  margin: 0 auto;
  box-sizing: border-box;
}

header .header_inner {
  font-weight: 600;
  position: relative;
}
/* スクロールするのに必要 */
/* @media (max-width: 960px){
  header .header_inner .menu{
    color: #ff0000;
    border-style: solid;
    display: flex;
    overflow-x:　scroll;
  }
} */
@media (max-width: 600px){
  .v-sheet.v-list:not(.v-sheet--outlined) > .navmenu{
    display: flex !important;
    overflow-x: auto;
    /* overflow-x:　scroll !important; */
    border-style: solid;
    border-color: red;
    width: 600px;
  }
}

  /* .v-sheet.v-list:not(.v-sheet--outlined) {
    display: flex;
    flex-wrap: wrap;
    border-style: solid;
    border-color: green;
    width: auto;
  } */

/* @media (max-width: 600px){
  .flex-container2 > .v-sheet.v-list:not(.v-sheet--outlined){
    display: flex;
    overflow-x:　scroll;
    border-style: solid;
    border-color: red;
  }
} */ */

/* header .flex-container2 {
  display: flex;
  overflow-x:　scroll;
} */
/* .menu-oya{
  display: flex;
  overflow-x:　scroll;
  border-style: solid;
  border-color: blue;
} */
/* .menu-ko{

} */
/*
.v-toolbar__content, .v-toolbar__extension{
  height: 56px;
  align-items: center;
  display: flex;
  position: relative;
  z-index: 0;
} */
/* @media (max-width: 960px){
  header .header_inner .flexbox {
     overflow-x: auto;
  }
} */

  /* header .header_inner .flexbox{
color: red;
  align-items: center;

}  */

/* header .header_inner .title{
  /* align-items:center;
  height: 56px; */
  /* margin:0;
  line-height:0;
  padding:8px 40px 8px 0;
} */

nav{
  position: fixed;
  right: 90px;
}

header .header_inner .auth_buttons{
  margin-left: auto;
  color: red;
  border-style: solid;
}
/* .naviflex{
  margin-right:200px;
} */
/* row（横） wrap（折り返す） */
.flexbox{
  display: flex;
  flex-wrap: wrap;
}

.flex-container2{
  height: 56px;
  flex-wrap: wrap;
  display: flex; /*--flexを指定--*/
}

/* 以下、body要素 */
 /*--親要素--*/
.flex-container {
	margin-top:100px;
  flex-wrap: wrap;
  display: flex; /*--flexを指定--*/
	background-color: #ffffff;
	border: solid 5px #fb6158;
	padding: 40px;
	box-sizing: border-box;
}

/*--子要素--*/
.flex-item {
	font-size: 20px;
	font-weight: bold;
	text-align: center;
	color: #ffffff;
	background-color: #1ece50;
	padding: 30px;
	box-sizing: border-box;
}
</style>
