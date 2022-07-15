<script setup>
  import Seat from './Seat.vue'
  import {tables} from '../tables.json'

  const props = defineProps({
    details: Object,
  })

  const table = tables.find(table => {
    return table.seats === props.details.seats && table.type === props.details.type
  })


</script>

<template>
  <div :class="props.details.type" class="table">
    <div class="table-name">{{props.details.name}}</div>
    <Seat class="seat" v-for="(seat, index) in props.details.seats"
          :number="index"
          :seats="props.details.seats"
          :members="props.details.members"
          :type="props.details.type"
    />
  </div>
</template>

<style>
  .table {
    position: absolute;
    left: v-bind('props.details.left');
    top: v-bind('props.details.top');
    border: 2px solid black;
  }

  .table-name {
    text-align: center;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .square {
    display: grid;
    grid-template-rows: repeat(v-bind('table.gridRows'), 30px);
    grid-template-columns: repeat(v-bind('table.gridColumns'), 30px);

  }

  .rectangle {
    display: grid;
    grid-template-rows: repeat(v-bind('table.gridRows'), 30px);
    grid-template-columns: repeat(v-bind('table.gridColumns'), 50px);
  }

  .rectangle-inverted {
    display: grid;
    grid-template-rows: repeat(v-bind('table.gridRows'), 50px);
    grid-template-columns: repeat(v-bind('table.gridColumns'), 30px);
  }

</style>