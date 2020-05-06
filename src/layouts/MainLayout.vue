<template>
  <q-layout view="lHh Lpr lFf" >
    <q-header elevated >
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen =! leftDrawerOpen"/>
        </q-toolbar>
       <div class="q-px-lg q-pt-xl q-mb-md">
        <div class="text-h3 myFont">Todo</div>
        <div class="text-subtitle1 q-px-lg ">{{ todaysDate }}</div>
        </div>
      <q-img src="statics/bg1.jpg" class="header-image absolute-top "></q-img>
    </q-header>
<q-drawer
        v-model="leftDrawerOpen"
        show-if-above
        :width="250"
        :breakpoint="600"
      >
        <q-scroll-area style="height: calc(100% - 192px); margin-top: 192px; border-right: 4px solid #ddd" >
          <q-list padding>
            <q-item to="/" exact clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="list" />
              </q-item-section>
              <q-item-section>
                Todo
              </q-item-section>
            </q-item>

            <q-item to="/help" exact clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="help" />
              </q-item-section>
              <q-item-section>
                Help
              </q-item-section>
            </q-item>

            <q-item to="/info" exact clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="info" />
              </q-item-section>
              <q-item-section>
                About us
              </q-item-section>
            </q-item>
          </q-list>
        </q-scroll-area>

        <q-img class="absolute-top" src="statics/bg1.jpg" style="height: 192px">
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="56px" class="q-mb-sm">
              <img src="statics/obito.jpg">
            </q-avatar>
            <div class="text-weight-bold">Andres Coronado</div>
            <div>@andresjcl</div>
          </div>
        </q-img>
      </q-drawer>
    <q-page-container>
      <keep-alive>
          <router-view />
      </keep-alive>
    </q-page-container>
  </q-layout>
</template>

<script>
import { date } from 'quasar'
// import EssentialLink from 'components/EssentialLink'

export default {
  name: 'MainLayout',

  // components: {
  //   EssentialLink
  // },
  computed: {
    todaysDate () {
      const timeStamp = Date.now()
      return date.formatDate(timeStamp, 'dddd D MMMM')
    }
  },

  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: [
        {
          title: 'Docs',
          caption: 'quasar.dev',
          icon: 'school',
          link: 'https://quasar.dev'
        },
        {
          title: 'Github',
          caption: 'github.com/quasarframework',
          icon: 'code',
          link: 'https://github.com/quasarframework'
        },
        {
          title: 'Discord Chat Channel',
          caption: 'chat.quasar.dev',
          icon: 'chat',
          link: 'https://chat.quasar.dev'
        },
        {
          title: 'Forum',
          caption: 'forum.quasar.dev',
          icon: 'record_voice_over',
          link: 'https://forum.quasar.dev'
        },
        {
          title: 'Twitter',
          caption: '@quasarframework',
          icon: 'rss_feed',
          link: 'https://twitter.quasar.dev'
        },
        {
          title: 'Facebook',
          caption: '@QuasarFramework',
          icon: 'public',
          link: 'https://facebook.quasar.dev'
        },
        {
          title: 'Quasar Awesome',
          caption: 'Community Quasar projects',
          icon: 'favorite',
          link: 'https://awesome.quasar.dev'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
  .header-image{
    height:100%;
    z-index: -1;
    // opacity:0.2;
    // filter: grayscale(100%);
    // background: none !important;
  }
  .myFont {
    font-family: 'Press Start 2P', cursive;
    font-family: 'Monoton', cursive;
    // font-family: 'Rubik Mono One', sans-serif;

  }
</style>
