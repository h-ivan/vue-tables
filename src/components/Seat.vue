<script setup>
import {seats} from '../seats.json';

  const props = defineProps({
    seats: Number,
    number: Number,
    type: String,
    members: Object
  })


  const currentSeat = seats.find(seat => {
    return seat.seats === props.seats && seat.seatNumber === ( props.number + 1)
        && seat.type === props.type
  })

  const currentMember = props.members.find(member => {
    return member.seat === ( props.number + 1)
  })


</script>

<template>
  <div class="seat">
    <input class="seat-name" type="text" v-model="currentMember.name">
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

.seat-name {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 14px;
  text-align: center;
  color: #000;
  background-color: #fff;
  border: 2px solid black;
  border-radius: 100%;
  padding: 0.5rem;
  width: 100%;
  height: 100%;
  outline: none;
}

</style>