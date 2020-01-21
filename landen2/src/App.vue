<template>
  <div id="app">
    <Landen v-bind:landen="landen" />
  </div>
</template>

<script>
import Landen from './components/Landen';


export default {
  name: 'app',
  components: {
    Landen
  },
  data() {
    return {
      landen: [
        {
          id: 1,
          title: "Nederland",
          completed: false
        },
        {
          id: 2,
          title: "Amerika",
          completed: true
        },
        {
          id: 3,
          title: "Belgie",
          completed: false
        }
      ]
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
