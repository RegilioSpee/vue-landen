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
import axios from 'axios';

export default {
  name: 'app',
  components: {
    Header,
    Landen,
    AddLand
  },
  data() {
    return {
      landen: []
    }
  },
  methods: {
    deleteLand(id) {
      this.landen = this.landen.filter(land => land.id !== id);
    },
    addLand(newLand) {
      const { title, completed } = newLand;

      axios.post('https://jsonplaceholder.typicode.com/todos', {
       title,
       completed 
      })
      .then(res => this.landen = [...this.landen, res.data]);
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res => this.landen = res.data)
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
