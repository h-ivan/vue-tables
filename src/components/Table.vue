<script setup>
import Seat from './Seat.vue'
import {tables} from '../tables.json'
import interact from "interactjs";


const emit = defineEmits()

const props = defineProps({
  details: Object,
})

const table = tables.find(table => {
  return table.seats === props.details.seats && table.type === props.details.type
})


interact('.draggable').draggable({
  listeners: {
    move(event) {

      let target = event.target,
      x = (parseFloat(target.getAttribute('data-x')) || 0) + event.dx,
      y = (parseFloat(target.getAttribute('data-y')) || 0) + event.dy;

      props.details.left = x + 'px'
      props.details.top = y + 'px'
      event.target.style.transform =
          `translate(${x}px, ${y}px)`
      target.setAttribute('data-x', x);
      target.setAttribute('data-y', y);

      emit('table-updated', props.details)
    },
  }
})

</script>

<template>

  <div :class="props.details.type" class="table draggable">
    <input type="text" class="table-name" v-model="props.details.name"/>
    <Seat class="seat" v-for="(seat, index) in props.details.seats"
          :number="index"
          :seats="props.details.seats"
          :members="props.details.members"
          :type="props.details.type"
    />
  </div>

</template>

<style scoped>
.table {
  position: absolute;
  left: v-bind('props.details.left');
  top: v-bind('props.details.top');
  border: 2px solid black;
  background: white;
}

.table-name {
  text-align: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  max-width: 80%;
}

.draggable {
  /* To prevent interact.js warnings */
  user-select: none;
  -ms-touch-action: none;
  touch-action: none;
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

.circle {
  display: grid;
  grid-template-rows: repeat(v-bind('table.gridRows'), 30px);
  grid-template-columns: repeat(v-bind('table.gridColumns'), 30px);
  border-radius: 100%;
}

</style>