<script setup>
  import {table} from '../db.json'
  import Table from "./Table.vue";

  defineProps({
    size: Object
  })


</script>

<template>
  <div class="room">
    <Table v-for="(table, index) in table" :details="table" :key="table.id" />
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