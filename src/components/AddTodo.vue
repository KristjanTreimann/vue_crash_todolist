<template>

    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Todo">
            <input type="submit" value="submit" class="btn">
        </form>
    </div>

</template>

<script>

//import uuid from 'uuid'
export default {
    name: 'AddTodo',
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault()
            const newTodo = {
                //id: uuid.v4(), no need when using api, where id is set
                title: this.title,
                completed: false

            }

        // Send up to parent
        this.$emit('add-todo', newTodo)

        // Clear form after submit
        this.title = ''
        }
    },
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
        flex: 2;
    }

</style>