<template>
    <div class="land-item" v-bind:class="{'is-complete':land.completed}">
      <p>
          <input type="checkbox" v-on:change="markComplete">
          {{land.title}}</p>  
          <button class="del">x</button>
    </div>
</template>

<script>
export default {
    name: "LandItem",
    props: ["land"],
    methods: {
        markComplete() {
            this.land.completed = !this.land.completed;
        }
    }
}
</script>

<style scoped>
.land-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}

.is-complete {
    text-decoration: line-through;
}

.del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
}
</style>