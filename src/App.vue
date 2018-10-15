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
        
        <v-list-tile>
          <v-btn icon @click.stop="miniVariant = !miniVariant" class="orange--text darken-2 right">
            <v-icon v-html="miniVariant ? 'fas fa-bars' : 'fas fa-chevron-left'"></v-icon>
          </v-btn>
        </v-list-tile>
        <br>
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
        > 
          <span v-if="page == item.page" 
                class="orange lighten-4" 
                style="border-bottom-left-radius:6px; border-top-left-radius:6px">
            <v-list-tile-action class="pa-2 ">
              <v-icon v-bind:title="item.title" v-html="item.icon" color="orange darken-2" ></v-icon>
            </v-list-tile-action>
          </span>
          <span v-else v-on:click="page=item.page" >
            <v-list-tile-action class="pa-2">
              <v-icon v-bind:title="item.title" v-html="item.icon" color="orange darken-2" ></v-icon>
            </v-list-tile-action>
          </span>
          
          <span v-if="page == item.page" 
                class="orange lighten-4"
                style="border-bottom-right-radius:6px; border-top-right-radius:6px">
            <v-list-tile-content class="pa-2 ">
              <v-list-tile-title v-text="item.title" class="orange--text"></v-list-tile-title>
            </v-list-tile-content>
          </span>
          <span v-else v-on:click="page=item.page">
            <v-list-tile-content class="pa-2">
              <v-list-tile-title v-text="item.title" class="orange--text"></v-list-tile-title>
            </v-list-tile-content>
          </span>          
        </v-list-tile>
        <br>
        <v-list-tile>
          <v-btn icon class="orange--text darken-2 right">
            <v-icon v-html="'fas fa-sign-out-alt'"></v-icon>
          </v-btn>
          <v-list-tile-content class="pa-2 ">
            <v-list-tile-title v-text="'Log Out'" class="orange--text"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    
    <v-content>
      <span v-if=     "page === 'home'">        <HelloWorld/> </span>
      <span v-else-if="page === 'widgets'">     <Widgets/> </span>
      <span v-else-if="page === 'advertisers'"> <Advertisers/> </span>
      <span v-else-if="page === 'partners'">    <Partners/> </span>
      <span v-else-if="page === 'bbt'">         <BBT/> </span>
      <span v-else-if="page === 'user'">        <User/> </span>
      <span v-else> Ooops! How did you even get here? </span>
    </v-content>
    
    
    <v-footer :fixed="fixed" app>
      <span> |||| Tech Ops 2018 || </span>
      <span> || Privacy Policy</span>
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
      rightDrawer: false
    }
  }
}
</script>
