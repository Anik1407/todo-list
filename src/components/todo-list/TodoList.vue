<template>
    <div class="todo-list">
        <TodoListForm 
            @update:todo-item="insertTodoItemInItemList($event)"
        />

        <TodoItemsList :items-to-show-in-list="todoItems"/>
    </div>
    
</template>

<script setup>
import {ref} from 'vue'
import TodoListForm from './TodoListForm.vue'
import TodoItemsList from './TodoItemsList.vue'

const todoItems = ref([])


function insertTodoItemInItemList(itemName){
    todoItems.value.unshift(itemName)
}

// function deleteItem(itemIndex){
//     console.log(itemIndex);
//     todoItems.value.splice(itemIndex, 1)
// }
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