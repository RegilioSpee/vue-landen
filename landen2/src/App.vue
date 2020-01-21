<template>
  <div id="app">
    {{msg}}
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {
    
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
