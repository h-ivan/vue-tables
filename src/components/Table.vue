<script setup>
  import Seat from './Seat.vue'
  import {tables} from '../tables.json'

  const props = defineProps({
    details: Object,
  })

  const table = tables.find(table => {
    return table.seats === props.details.seats && table.type === props.details.type
  })

  const bgImage = `url(${props.details.image})`;


</script>

<template>
  <div :class="props.details.type" class="table">
<!--    <img :src="props.details.image" alt="Avatar" style="width:100%">-->
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
    background: v-bind('bgImage') no-repeat;
    background-size: cover;
  }

  .square {
    width: v-bind('table.width');
    height: v-bind('table.height');
    display: grid;
    grid-template-rows: repeat(v-bind('table.gridColumns'), 1fr);
    grid-template-columns: repeat(v-bind('table.gridRows'), 1fr);
    justify-items: center;
  }

</style>