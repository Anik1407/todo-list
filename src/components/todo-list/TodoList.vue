<template>
    <div class="todo-list">
        <div class="todo-list__action">
            <input
                v-bind:value="todoItem"
                type="text"
                class=""
                v-on:input="updateTodoItem($event.target.value)"
            >

            <button
                class="todo-list__action__button"
                v-on:click="insertTodoItemInItemList"
            >
            Add todo
            </button>
        </div>

        <div class="todo-list__items">
            <li class="todo-list__items__list">
                <ul v-if="!todoItems.length">
                    no data
                </ul>

                <ul
                    v-for="item,index in todoItems"
                    :key="item"
                >
                    <div class="">{{index }} -{{ item }}</div>
                    <input type="button" value="Delete" @click="deleteItem(index)">
                </ul>
            </li>
        </div>
    </div>
    
</template>

<script setup>
import {ref} from 'vue'

const todoItem = ref('')
const todoItems = ref([])

function updateTodoItem(item){
    todoItem.value = item
}

function insertTodoItemInItemList(){
    todoItems.value.unshift(todoItem.value)
    todoItem.value = ''
}

function deleteItem(itemIndex){
    console.log(itemIndex);
    todoItems.value.splice(itemIndex, 1)
}
</script>

<style lang="scss" scoped>
.todo-list__action{
    display: flex;
    
}

.todo-list__button{
    margin-inline: 1rem;
}

.todo-list__action__items{
    margin: 2rem;
    border: 1px solid lightgreen;
}

.todo-list__items__list{
    list-style-type: none;
}
</style>