<template>
  <div id="app">
    <Header />
    <AddLand v-on:add-land="addLand"/>
    <Landen v-bind:landen="landen" v-on:del-land="deleteLand" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Landen from './components/Landen';
import AddLand from './components/AddLand';


export default {
  name: 'app',
  components: {
    Header,
    Landen,
    AddLand
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
  },
  methods: {
    deleteLand(id) {
      this.landen = this.landen.filter(land => land.id !== id);
    },
    addLand(newLand) {
      this.landen = [...this.landen, newLand];
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

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
