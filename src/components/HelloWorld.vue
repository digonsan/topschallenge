
<template>

  <v-container fluid>
    <v-slide-y-transition mode="out-in">
      <v-layout column align-center>     
        <v-container row grid-list-md text-xs-center>
          <v-layout justify-space-around>
            <v-flex xs6 >
              <h1>Welcome to TOPS :)</h1>
            </v-flex>
          </v-layout>
        </v-container>

        <v-container row grid-list-md text-xs-center>
          <v-layout justify-space-around>
            <v-flex  v-for="i in timezones" :key="`1${i}`" xs2>
              <v-card >
                <v-card-text class="px-0">
                  <div class="blue-grey lighten-4" style="border-radius:8px">
                    <br>
                    <p style="font-family:'Space Mono', monospace" class="grey darken-4 green--text ma-2 pa-1" >
                      {{i.time}}
                    </p>
                    <p style="font-family:'Markazi Text', serif" class="pa-1">{{i.place}}</p>
                  </div>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>

        <v-container row grid-list-md text-xs-center>
          <v-layout justify-space-around>
            <v-flex xs12 class="orange darken-2 white--text">
              <h2>Quick Links</h2>
            </v-flex>
          </v-layout>
        </v-container>

        <v-container v-if="admin" row grid-list-md text-xs-center>
          <v-layout justify-space-around>
            <v-flex xs12 class="orange darken-2 white--text">
              <h2>Admin Options</h2>
            </v-flex>
          </v-layout>
        </v-container>

      </v-layout>
    </v-slide-y-transition>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    function renderTime(zone) {
      var currentTime = new Date();
      var h = currentTime.getUTCHours();
      var m = currentTime.getUTCMinutes();
      var s = currentTime.getUTCSeconds();
      if (h < 10) {
          h = "0" + h;
      }
      if (m < 10) {
          m = "0" + m;
      }
      if (s < 10) {
          s = "0" + s;
      }
      return (h+zone)%24+ ":" + m + ":" + s + " ";
    }
    //*** time needs to update :(
    return{
      admin: true, //*** make it populate depending on user
      timezones:[
        {place:'San Francisco', time: renderTime(-7)},
        {place:'Omaha',time:renderTime(-5)},
        {place:'New York', time:renderTime(-4)},
        {place:'London', time: renderTime(1)},
        {place:'Paris', time: renderTime(2)},
        {place:'Istambul', time: renderTime(3)},
        {place:'Dubai', time: renderTime(4)},
        {place:'Jakarta', time: renderTime(7)},
        {place:'Singapore', time: renderTime(8)},
        {place:'Sydney', time: renderTime(11)}
      ],
      quick_links:[ //*** top 6 of the current user if they don't have 6 do less or random
        {title:'Link 1', desc: 'blah blah blah blah', pic: '*pic*'},
        {title:'Link 2', desc: 'blah blah blah blah', pic: '*pic*'},
        {title:'Link 3', desc: 'blah blah blah blah', pic: '*pic*'},
        {title:'Link 4', desc: 'blah blah blah blah', pic: '*pic*'},
        {title:'Link 5', desc: 'blah blah blah blah', pic: '*pic*'},
        {title:'Link 6', desc: 'blah blah blah blah', pic: '*pic*'}
      ],
      admin_options:[
        {title:'Users', pic: '*pic*'},
        {title:'Plugins',pic: '*pic*'},
        {title:'Py Scripts', pic: '*pic*'},
        {title:'Table Sizes', pic: '*pic*'},
        {title:'Logs', pic: '*pic*'}
      ]
    }
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
