<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>

  <div>
    <v-quagga :onDetected="logIt" :readerSize="readerSize" :readerTypes="['ean_reader']"></v-quagga>
  </div>

  </div>

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Vue from 'vue'
import VueQuagga from 'vue-quaggajs'

Vue.use(VueQuagga)

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data () {
    return {
      readerSize: {
        width: 440,
        height: 680
      },
      detecteds: []
    }
  },
  methods: {
    logIt (data) {
      console.log('detected', data)
    }
  }
}
</script>
