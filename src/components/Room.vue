<script setup>
import {tables} from '../db.json'
import Table from "./Table.vue";
import {ref} from "vue";

defineProps({
  size: Object
})

const updateTable = (table) => {
  console.log(table)
  // API CALL to update position
}
</script>

<template>
  <div class="room">
    <Table @tableUpdated="updateTable" :id="'table_'+table.id"
           v-for="(table, index) in tables"
           :details="table" :key="table.id"/>
  </div>
</template>

<style>

.room {
  width: v-bind('size.width');
  height: v-bind('size.height');
  background-color: #f3f3f3;
  border: 2px solid black;
  position: relative;

}

</style>