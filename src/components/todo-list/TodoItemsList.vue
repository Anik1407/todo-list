<template>
    <div class="todo-list__items">
            <li class="todo-list__items__list">
                <ul v-if="!itemsToShowInList.length">
                    no data
                </ul>

                <ul
                    v-for="item,index in itemsToShowInList"
                    :key="item"
                >
                    <div class="">{{index }} -{{ item }}</div>
                    <input type="button" value="Delete">
                    <!-- @click="deleteItem(index)" -->
                </ul>
            </li>
    </div>
</template>

<script setup>

//Example runtime declaration: using Array syntax
defineProps(['itemsToShowInList'])

</script>