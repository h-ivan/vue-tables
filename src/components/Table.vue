<script setup>
import Seat from './Seat.vue'

const tables = [
  {
    "type": "square",
    "seats": 2,
    "gridColumns": 3,
    "gridRows": 3
  },
  {
    "type": "square",
    "seats": 4,
    "gridColumns": 3,
    "gridRows": 3
  },
  {
    "type": "square",
    "seats": 6,
    "gridColumns": 5,
    "gridRows": 5
  },
  {
    "type": "square",
    "seats": 8,
    "gridColumns": 5,
    "gridRows": 5
  },
  {
    "type": "square",
    "seats": 10,
    "gridColumns": 7,
    "gridRows": 7
  },
  {
    "type": "square",
    "seats": 12,
    "gridColumns": 7,
    "gridRows": 7
  },
  {
    "type": "rectangle",
    "seats": 2,
    "gridColumns": 3,
    "gridRows": 3
  },
  {
    "type": "rectangle",
    "seats": 4,
    "gridColumns": 3,
    "gridRows": 3
  },
  {
    "type": "rectangle",
    "seats": 6,
    "gridColumns": 5,
    "gridRows": 3
  },
  {
    "type": "rectangle",
    "seats": 8,
    "gridColumns": 5,
    "gridRows": 3
  },
  {
    "type": "rectangle",
    "seats": 10,
    "gridColumns": 7,
    "gridRows": 3
  },
  {
    "type": "rectangle",
    "seats": 12,
    "gridColumns": 8,
    "gridRows": 3
  },
  {
    "type": "rectangle-inverted",
    "seats": 2,
    "gridColumns": 3,
    "gridRows": 3
  },
  {
    "type": "rectangle-inverted",
    "seats": 4,
    "gridColumns": 3,
    "gridRows": 3
  },
  {
    "type": "rectangle-inverted",
    "seats": 6,
    "gridColumns": 3,
    "gridRows": 5
  },
  {
    "type": "rectangle-inverted",
    "seats": 8,
    "gridColumns": 3,
    "gridRows": 5
  },
  {
    "type": "rectangle-inverted",
    "seats": 10,
    "gridColumns": 3,
    "gridRows": 7
  },
  {
    "type": "rectangle-inverted",
    "seats": 12,
    "gridColumns": 3,
    "gridRows": 8
  },
  {
    "type": "circle",
    "seats": 2,
    "gridColumns": 3,
    "gridRows": 3
  },
  {
    "type": "circle",
    "seats": 4,
    "gridColumns": 3,
    "gridRows": 3
  },
  {
    "type": "circle",
    "seats": 6,
    "gridColumns": 5,
    "gridRows": 5
  },
  {
    "type": "circle",
    "seats": 8,
    "gridColumns": 5,
    "gridRows": 5
  },
  {
    "type": "circle",
    "seats": 10,
    "gridColumns": 7,
    "gridRows": 7
  },
  {
    "type": "circle",
    "seats": 12,
    "gridColumns": 7,
    "gridRows": 7
  }
]

const emit = defineEmits()

const props = defineProps({
  details: Object,
})

const table = tables.find(table => {
  return table.seats === props.details.seats && table.type === props.details.type
})
</script>

<template>
  <div :class="props.details.type" class="room-table draggable" :data-table="props.details.id">
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
.room-table {
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