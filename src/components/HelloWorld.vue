<template>
  <v-container fluid>
    <v-slide-y-transition mode="out-in">
      <v-layout column align-center>
        
        
        <v-container grid-list-md text-xs-center>
          <v-layout row wrap>
            <v-flex xs12>
              <v-card dark color="primary">
                <v-card-text class="px-0">Fun Clocks!</v-card-text>
              </v-card>
            </v-flex>
            <v-flex v-for="i in timezones" :key="`1${i}`" xs1>
              <v-card dark color="secondary">
                <v-card-text class="px-0">in {{i.place}} it is {{i.time}}</v-card-text>
              </v-card>
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
    return{
      timezones:[{place:'berlin', time:'11'},{place:'london',time:'10'}]
    }
  }
}


//berlin istambul paris italy
//dublin london
//dubai
//nyc
//omaha mexico city
//san francisco
//singapore
//australia indonesia
//hong kong south korea
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
