<script setup>
  import Seat from './Seat.vue'
  import {tables} from '../tables.json'

  const props = defineProps({
    style: Object,
  })

  const table = tables.find(table => {
    return table.seats === props.style.seats && table.type === props.style.type
  })


</script>

<template>
  <div :class="style.type" class="table">
    <Seat class="seat" v-for="(seat, index) in style.seats" :number="index" :seats="style.seats" :type="style.type" />
  </div>
</template>

<style>
  .table {
    position: absolute;
    left: v-bind('style.left');
    top: v-bind('style.top');
    border: 2px solid black;
  }

  .rectangle {
    width: 250px;
    height: 150px;

  }

  .square {
    width: 300px;
    height: 300px;
    display: grid;
    grid-template-rows: repeat(v-bind('table.gridColumns'), 1fr);
    grid-template-columns: repeat(v-bind('table.gridRows'), 1fr);
    justify-items: center;
  }

</style>