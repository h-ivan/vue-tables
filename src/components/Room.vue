<script setup>
import interact from "interactjs";

import Table from "./Table.vue";
import {ref, onMounted, toRefs} from "vue";
//import axios from 'axios'
//import Swal from 'sweetalert2';

let tables = ref([])


const seats = {
  'square': 2,
  'circle': 2,
  'rectangle': 2
}


const props = defineProps({
  size: Object,
  map: String
})

const {map} = toRefs(props);

onMounted(() => {

  // tables.value.forEach((table) => {
  interact('.draggable').draggable({
    listeners: {
      move(event) {
        let target = event.target,
            x = (parseFloat(target.getAttribute('data-x')) || 0) + event.dx,
            y = (parseFloat(target.getAttribute('data-y')) || 0) + event.dy;

        let table = tables.value.filter((t) => {
          return t.id == target.getAttribute('data-table')
        })
        table = table[0]


        event.target.style.transform =
            `translate(${x}px, ${y}px)`
        target.setAttribute('data-x', x);
        target.setAttribute('data-y', y);
        // emit('table-updated', props.details)
        //table.left = x + 'px'
        //table.top = y + 'px'
      },
    }
    //})
  })

})


const addTable = (type) => {

  let new_table = {
    "name": "",
    "type": type,
    "seats": parseInt(seats[type]),
    "members": [],
    "left": "230px",
    "top": "100px",
    "id": Date.now()
  }

  for (let i = 1; i <= new_table.seats; i++) {
    new_table.members.push({
      'name': '',
      'seat': i
    })
  }
  tables.value.push(new_table)

}

const updateTable = (table) => {
  // API CALL to update position
}

const deleteTable = (table) => {
  tables.value.splice(tables.value.indexOf(table), 1)
}

const saveTables = () => {
 /* axios.post('/eventSetting/eventRoomMapEdit/' + map.value + '/update-tables', {
    tables: tables.value
  })
      .then(response => Swal.fire(
          'Tavoli aggiornati correttamente',
          '',
          'success'
      ))
      .catch(error => {
        Swal.fire(
            error.message,
            '',
            'success'
        )
      });*/
}
</script>

<template>
  <div>
    <div class="toolbar">
      <div class="row">
        <div class="col-md-12 text-right">
          <button class="btn btn-success" @click="saveTables">Salva</button>
        </div>
        <div class="col-md-4">
          <fieldset>
            <legend>
              <h5>Tavoli Quadrati</h5>
            </legend>

            <div class="row">

              <div class="col-md-8">
                <select class="form-control" v-model="seats['square']">
                  <option value="2">2 Posti</option>
                  <option value="4">4 Posti</option>
                  <option value="6">6 Posti</option>
                  <option value="8">8 Posti</option>
                  <option value="10">10 Posti</option>
                  <option value="12">12 Posti</option>
                </select>
              </div>
              <div class="col-md-4">
                <button class="btn btn-primary mt-0" @click="addTable('square')">Aggiungi</button>
              </div>
            </div>

          </fieldset>

        </div>
        <div class="col-md-4">
          <fieldset>
            <legend>
              <h5>Tavoli Tondi</h5>
            </legend>
            <div class="row">
              <div class="col-md-8">
                <select class="form-control" v-model="seats['circle']">
                  <option value="2">2 Posti</option>
                  <option value="4">4 Posti</option>
                  <option value="6">6 Posti</option>
                  <option value="8">8 Posti</option>
                  <option value="10">10 Posti</option>
                  <option value="12">12 Posti</option>
                </select>
              </div>
              <div class="col-md-4">
                <button class="btn btn-primary mt-0" @click="addTable('circle')">Aggiungi</button>
              </div>
            </div>
          </fieldset>

        </div>
        <div class="col-md-4">
          <fieldset>
            <legend>
              <h5>Tavoli Rettangolari</h5>
            </legend>
            <div class="row">
              <div class="col-md-8">
                <select class="form-control" v-model="seats['rectangle']">
                  <option value="2">2 Posti</option>
                  <option value="4">4 Posti</option>
                  <option value="6">6 Posti</option>
                  <option value="8">8 Posti</option>
                  <option value="10">10 Posti</option>
                  <option value="12">12 Posti</option>
                </select>
              </div>
              <div class="col-md-4">
                <button class="btn btn-primary mt-0" @click="addTable('rectangle')">Aggiungi</button>
              </div>
            </div>
          </fieldset>

        </div>
      </div>
    </div>

    <div class="room">

      <div v-for="(table, index) in tables">
        <Table @tableDeleted="deleteTable" :id="'table_'+index"
               :details="table" :key="index"/>
      </div>


    </div>

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

.mt-0 {
  margin-top: 0px;
}
</style>