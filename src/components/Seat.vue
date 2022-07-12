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

  const transform =`rotate(${currentSeat.nameRotate}) translate(${currentSeat.nameTranslate})`


</script>

<template>
  <div class="seat">
    <input :class="`seat-name ${currentSeat.namePosition}`" type="text" v-model="currentMember.name">
  </div>
</template>

<style>

.seat {
  position: relative;
  box-sizing: border-box;
  width: 30px;
  height: 30px;
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
  top: v-bind('currentSeat.namePositionTop');
  left: v-bind('currentSeat.namePositionLeft');
  transform: v-bind('transform');
  font-size: 11px;
  text-align: center;
  color: #000;
  width: 60px;
  outline: none;
}

.name-top {
  top: -25px;
  left: -23px;
  transform: rotate(-30deg);
}

.name-bottom {
  top: 32px;
  left: -14px;
  transform: rotate(-30deg);
}

.name-right {
  top: -32px;
  left: 15px;
  transform: rotate(-30deg);
}

.name-left {
  top: -6px;
  left: -55px;
  transform: rotate(-30deg);
}

</style>