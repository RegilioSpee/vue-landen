<template>
    <div>
        <form @submit="addLand">
            <input type="text" v-model="title" name="title" placeholder="Voeg land toe...">
        <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
// import uuid from 'uuid';
export default {
    name: "AddLand",
    data() {
        return {
           title: '' 
        }
    },
    methods: {
        addLand(e) {
            e.preventDefault();
            const newLand = {
                title: this.title,
                completed: false
            }
            // Send up to parent
            this.$emit('add-land', newLand);

            this.title = '';
        }
    }
}
</script>

<style scoped>
form {
    display: flex;
}

input[type="text"] {
    flex: 10;
    padding: 5px;
}

input[type="submit"] {
    /* flex 2; */
}
</style>