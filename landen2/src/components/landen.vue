<template>
<div>
    <div v-bind:key="land.id" v-for="land in landen">
        <LandItem v-bind:land="land"/>
    </div>
    </div>
</template>

<script>
import LandItem from './LandItem.vue';

export default {
    name: "Landen",
    components: {
        LandItem
    },
    props: ["landen"]
}
</script>

<style scoped>

</style>