<template>
    <div>
        <form @submit="addTodo">
            <input v-model="title" type="text" name="title" placeholder="Add TOdo...">
            <input type="submit" value="submit" class="btn">
        </form>

    </div>
</template>
<script>
// import { v4 as uuidv4 } from 'uuid'
export default {
    name: "addtodo",
    data: function () {
        return {
            title: ""
        }
    },
    methods: {
        addTodo: function(e) {
            e.preventDefault()
            const newTodo= {
                title: this.title,
                completed: false
            }
            // send up to parent
            this.$emit('add-todo', newTodo)
            this.title= ''
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

</style>