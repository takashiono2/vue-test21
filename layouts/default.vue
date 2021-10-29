<template>
  <v-app>
    <header class="header pc_hyoji mini">
      <div class="header_inner">
        <div class="header_inner_head flexbox">
          <v-app-bar
            color="primary"
            :clipped-left="clipped"
            fixed
            app
            class="flexbox"
            id="nav-drawer"
          >

          <!-- <v-container> -->

            <v-toolbar-title class="title flexbox">Vuetify</v-toolbar-title>

                <v-layout class ="flexbox">
                  <v-list dense class ="flexbox">
                    <!-- <v-list v-if="$vuetify.breakpoint.mdAndUp" dense class="d-flex ml-8"> -->
                    <v-list-item v-for="menu in menus" :key="menu.title" class="menu gnav flexbox">
                      <v-btn text class="menu_item flexbox">
                        <v-icon class ="flexbox">{{ menu.icon }}</v-icon>
                          {{ menu.title }}
                      </v-btn>
                    </v-list-item>
                  </v-list>

                </v-layout>
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

.menu_item{
  align-items: center;
  height: 100%;
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

header{
 position: sticky;
}

header .pc_hyoji{
  display: block;
}

#nav-drawer{
  width: 100%;
  align-items: center;
}
.auth_buttons{
  margin-left: auto;
}

header .header_inner{
  align-items: center;
  height: 72px;
}

header .header_inner_head{
  align-items: center;
  height: 72px;
}

header .header_inner .title{
  align-items:center;
  height: 56px;
  margin:0;
  line-height:0;
  padding:8px 40px 8px 0;
}

nav{
  position: fixed;
  right: 90px;
}
/* .naviflex{
  margin-right:200px;
} */
/* row（横） wrap（折り返す） */
.flexbox{
  display: flex;
  flex-wrap: wrap;
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
