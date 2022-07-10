<script setup>
import {seats} from '../seats.json';

  const props = defineProps({
    seats: Number,
    number: Number,
    type: String
  })


  const currentSeat = seats.find(seat => {
    return seat.seats === props.seats && seat.seatNumber === ( props.number + 1)
        && seat.type === props.type
  })


</script>

<template>
  <div class="seat">
    {{currentSeat.seatNumber}}
  </div>
</template>

<style>

.seat {
  position: relative;
  box-sizing: border-box;
  width: 100px;
  height: 100px;
  border-radius: 100%;
  background-color: #f3f3f3;
  border: 2px solid black;
  grid-column-start: v-bind('currentSeat.columnPosition');
  grid-row-start: v-bind('currentSeat.rowPosition');
  top: v-bind('currentSeat.top');
  left: v-bind('currentSeat.left');
}

</style>