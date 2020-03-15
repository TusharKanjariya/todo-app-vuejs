<template>
    <li class="list-group-item">
        <input type="checkbox" v-on:change="doneComplete" v-bind:checked="todo.isComplete">
        <span v-bind:class="{'deleted':todo.isComplete}">{{todo.title}}</span>
        <button class="btn btn-danger btn-sm float-right" @click="$emit('deleteTodo',todo.id)">Delete</button>
    </li>
</template>

<script>
export default {
    name:'todo',
    props:['todo'],
    methods:{
        doneComplete(){
            this.todo.isComplete = !this.todo.isComplete;
        }
    }
}
</script>
<style scoped>
    .deleted{
        text-decoration: line-through;
    }
</style>