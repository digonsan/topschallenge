<template>
  <v-container fluid>
    <v-slide-y-transition mode="out-in">
      <v-layout row align-center>
        <v-layout column align-center xs6>
        </v-layout>
        <v-layout column xs6 >

          <v-layout row justify-center >
            <v-flex v-for="i in icons1" :key="`1${i}`" xs1>
              <v-icon v-html="i"></v-icon>
            </v-flex>
          </v-layout>
          <v-layout row justify-center >
            <v-flex v-for="i in icons2" :key="`1${i}`" xs1>
              <v-icon v-html="i"></v-icon>
            </v-flex>
          </v-layout>
          <v-layout row justify-center >
            <v-flex v-for="i in icons3" :key="`1${i}`" xs1>
              <v-icon v-html="i"></v-icon>
            </v-flex>
          </v-layout>
          <v-layout row justify-center >
            <v-flex v-for="i in icons4" :key="`1${i}`" xs1>
              <v-icon v-html="i"></v-icon>
            </v-flex>
          </v-layout>
          <v-layout row justify-center >
            <v-flex v-for="i in icons5" :key="`1${i}`" xs1>
              <v-icon v-html="i"></v-icon>
            </v-flex>
          </v-layout>

        </v-layout>
      </v-layout>
    </v-slide-y-transition>
  </v-container>
</template>

<script>
export default {
  name: 'User',
  props: {
    msg: String
  },
  data(){
    return{
      icons1:[
      "fas fa-user",
      "fas fa-user-astronaut",
      "fas fa-user-tie",
      "fas fa-user-ninja"
      ],
      icons2:[
        "fas fa-swimmer",
        "fas fa-ghost",
        "fas fa-smile",
        "fas fa-grimace"
      ],
      icons3:[
        "fas fa-dragon",
        "fas fa-horse",
        "fas fa-hippo",
        "fas fa-frog"
      ],
      icons4:[
        "fas fa-user-secret",
        "fas fa-theater-masks",
        "fas fa-laugh-beam",
        "fas fa-kiwi-bird"
      ],
      icons5:[
        "fas fa-grin-stars",
        "fas fa-cat",
        "fas fa-dog",
        "fas fa-poo"
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