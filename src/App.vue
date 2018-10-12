<template>
  <v-app>
    <v-navigation-drawer
      persistent
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
        >
          <span v-if="page == item.page">
            <v-list-tile-action class="orange lighten-2">
              <v-icon v-bind:title="item.title" v-html="item.icon" color="orange darken-2" ></v-icon>
            </v-list-tile-action>
          </span>
          <span v-else>
            <v-list-tile-action >
              <v-icon v-bind:title="item.title" v-html="item.icon" color="orange darken-2" ></v-icon>
            </v-list-tile-action>
          </span>

          <v-list-tile-content >
            <v-list-tile-title v-text="item.title" class="orange--text"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      app
      :clipped-left="clipped"
    >
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon v-html="miniVariant ? 'fas fa-bars' : 'fas fa-chevron-left'"></v-icon>
      </v-btn> 
      <v-toolbar-title v-text="title"></v-toolbar-title>
    </v-toolbar>
    
    <v-content>
      <span v-if=     "page === 'home'">        <HelloWorld/> </span>
      <span v-else-if="page === 'widgets'">     <Widgets/> </span>
      <span v-else-if="page === 'advertisers'"> <Advertisers/> </span>
      <span v-else-if="page === 'partners'">    <Partners/> </span>
      <span v-else-if="page === 'bbt'">         <BBT/> </span>
      <span v-else-if="page === 'user'">        <User/> </span>
      <span v-else> Ooops! How did you even get here? </span>
    </v-content>
    
    <v-navigation-drawer
      temporary
      :right="right"
      v-model="rightDrawer"
      fixed
      app
    >
      <v-list>
        <v-list-tile @click="right = !right">
          <v-list-tile-action>
            <v-icon>fas fa-exchange-alt</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>



<script>
import HelloWorld from './components/HelloWorld'
import Widgets from './components/Widgets'
import Advertisers from './components/Advertisers'
import Partners from './components/Partners'
import BBT from './components/BBT'
import User from './components/User'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Widgets,
    Advertisers,
    Partners,
    BBT,
    User
  },
  data () {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      page: 'home',
      items: [
      {
        icon: 'fas fa-home',
        title: 'Home',
        page: 'home'
      },
      {
        icon: 'fas fa-shapes',
        title: 'Widgets',
        page: 'widgets'
      },
      {
        icon: 'fas fa-ad',
        title: 'Advertisers',
        page: 'advertisers'
      },
      {
        icon: 'fas fa-handshake',
        title: 'Partners',
        page: 'partners'
      },
      {
        icon: 'fas fa-wrench',
        title: 'Built By Tech Ops!',
        page: 'bbt'
      },
      {
        icon: 'fas fa-user-astronaut',
        title: 'User Preferences',
        page: 'user'
      }],
      miniVariant: true,
      right: true,
      rightDrawer: false,
      title: 'Welcome to TOPS :)'
    }
  }
}
</script>
