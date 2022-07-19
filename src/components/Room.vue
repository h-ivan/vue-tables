<script setup>
import interact from "interactjs";

let tables = ref([
  {
    "id": 1,
    "name": "AAAAA",
    "type": "square",
    "seats": 2,
    "members": [
      {
        "name": "Name 1",
        "seat": 1
      },
      {
        "name": "Name 2",
        "seat": 2
      }
    ],
    "left": "230px",
    "top": "100px"
  },
  {
    "id": 2,
    "name": "Table 2",
    "type": "square",
    "seats": 4,
    "members": [
      {
        "name": "Name 3",
        "seat": 1
      },
      {
        "name": "Name 4",
        "seat": 2
      },
      {
        "name": "Name 5",
        "seat": 3
      },
      {
        "name": "Name 6",
        "seat": 4
      }
    ],
    "left": "280px",
    "top": "100px"
  },
  {
    "id": 3,
    "name": "Table 3",
    "type": "square",
    "seats": 6,
    "members": [
      {
        "name": "Name 7",
        "seat": 1
      },
      {
        "name": "Name 8",
        "seat": 2
      },
      {
        "name": "Name 9",
        "seat": 3
      },
      {
        "name": "Name 10",
        "seat": 4
      },
      {
        "name": "Name 11",
        "seat": 5
      },
      {
        "name": "Name 12",
        "seat": 6
      }
    ],
    "left": "500px",
    "top": "100px"
  },
  {
    "id": 4,
    "name": "Table 4",
    "type": "square",
    "seats": 8,
    "members": [
      {
        "name": "Name 13",
        "seat": 1
      },
      {
        "name": "Name 14",
        "seat": 2
      },
      {
        "name": "Name 15",
        "seat": 3
      },
      {
        "name": "Name 16",
        "seat": 4
      },
      {
        "name": "Name 17",
        "seat": 5
      },
      {
        "name": "Name 18",
        "seat": 6
      },
      {
        "name": "Name 19",
        "seat": 7
      },
      {
        "name": "Name 20",
        "seat": 8
      }
    ],
    "left": "820px",
    "top": "100px"
  },
  {
    "id": 5,
    "name": "Table 5",
    "type": "square",
    "seats": 10,
    "members": [
      {
        "name": "Name 21",
        "seat": 1
      },
      {
        "name": "Name 22",
        "seat": 2
      },
      {
        "name": "Name 23",
        "seat": 3
      },
      {
        "name": "Name 24",
        "seat": 4
      },
      {
        "name": "Name 25",
        "seat": 5
      },
      {
        "name": "Name 26",
        "seat": 6
      },
      {
        "name": "Name 27",
        "seat": 7
      },
      {
        "name": "Name 28",
        "seat": 8
      },
      {
        "name": "Name 29",
        "seat": 9
      },
      {
        "name": "Name 30",
        "seat": 10
      }
    ],
    "left": "80px",
    "top": "370px"
  },
  {
    "id": 6,
    "name": "Table 6",
    "type": "square",
    "seats": 12,
    "members": [
      {
        "name": "Name 31",
        "seat": 1
      },
      {
        "name": "Name 32",
        "seat": 2
      },
      {
        "name": "Name 33",
        "seat": 3
      },
      {
        "name": "Name 34",
        "seat": 4
      },
      {
        "name": "Name 35",
        "seat": 5
      },
      {
        "name": "Name 36",
        "seat": 6
      },
      {
        "name": "Name 37",
        "seat": 7
      },
      {
        "name": "Name 38",
        "seat": 8
      },
      {
        "name": "Name 39",
        "seat": 9
      },
      {
        "name": "Name 40",
        "seat": 10
      },
      {
        "name": "Name 41",
        "seat": 11
      },
      {
        "name": "Name 42",
        "seat": 12
      }
    ],
    "left": "450px",
    "top": "370px"
  },
  {
    "id": 7,
    "name": "Table 7",
    "type": "rectangle",
    "seats": 2,
    "members": [
      {
        "name": "Name 43",
        "seat": 1
      },
      {
        "name": "Name 44",
        "seat": 2
      }
    ],
    "left": "80px",
    "top": "700px"
  },
  {
    "id": 8,
    "name": "Table 8",
    "type": "rectangle",
    "seats": 4,
    "members": [
      {
        "name": "Name 45",
        "seat": 1
      },
      {
        "name": "Name 46",
        "seat": 2
      },
      {
        "name": "Name 47",
        "seat": 3
      },
      {
        "name": "Name 48",
        "seat": 4
      }
    ],
    "left": "320px",
    "top": "700px"
  },
  {
    "id": 9,
    "name": "Table 9",
    "type": "rectangle",
    "seats": 6,
    "members": [
      {
        "name": "Name 49",
        "seat": 1
      },
      {
        "name": "Name 50",
        "seat": 2
      },
      {
        "name": "Name 51",
        "seat": 3
      },
      {
        "name": "Name 52",
        "seat": 4
      },
      {
        "name": "Name 53",
        "seat": 5
      },
      {
        "name": "Name 54",
        "seat": 6
      }
    ],
    "left": "580px",
    "top": "700px"
  },
  {
    "id": 10,
    "name": "Table 10",
    "type": "rectangle",
    "seats": 8,
    "members": [
      {
        "name": "Name 55",
        "seat": 1
      },
      {
        "name": "Name 56",
        "seat": 2
      },
      {
        "name": "Name 57",
        "seat": 3
      },
      {
        "name": "Name 58",
        "seat": 4
      },
      {
        "name": "Name 59",
        "seat": 5
      },
      {
        "name": "Name 60",
        "seat": 6
      },
      {
        "name": "Name 61",
        "seat": 7
      },
      {
        "name": "Name 62",
        "seat": 8
      }
    ],
    "left": "80px",
    "top": "940px"
  },
  {
    "id": 11,
    "name": "Table 11",
    "type": "rectangle",
    "seats": 10,
    "members": [
      {
        "name": "Name 63",
        "seat": 1
      },
      {
        "name": "Name 64",
        "seat": 2
      },
      {
        "name": "Name 65",
        "seat": 3
      },
      {
        "name": "Name 66",
        "seat": 4
      },
      {
        "name": "Name 67",
        "seat": 5
      },
      {
        "name": "Name 68",
        "seat": 6
      },
      {
        "name": "Name 69",
        "seat": 7
      },
      {
        "name": "Name 70",
        "seat": 8
      },
      {
        "name": "Name 71",
        "seat": 9
      },
      {
        "name": "Name 72",
        "seat": 10
      }
    ],
    "left": "480px",
    "top": "940px"
  },
  {
    "id": 12,
    "name": "Table 12",
    "type": "rectangle",
    "seats": 12,
    "members": [
      {
        "name": "Name 73",
        "seat": 1
      },
      {
        "name": "Name 74",
        "seat": 2
      },
      {
        "name": "Name 75",
        "seat": 3
      },
      {
        "name": "Name 76",
        "seat": 4
      },
      {
        "name": "Name 77",
        "seat": 5
      },
      {
        "name": "Name 78",
        "seat": 6
      },
      {
        "name": "Name 79",
        "seat": 7
      },
      {
        "name": "Name 80",
        "seat": 8
      },
      {
        "name": "Name 81",
        "seat": 9
      },
      {
        "name": "Name 82",
        "seat": 10
      },
      {
        "name": "Name 83",
        "seat": 11
      },
      {
        "name": "Name 84",
        "seat": 12
      }
    ],
    "left": "80px",
    "top": "1160px"
  },
  {
    "id": 13,
    "name": "Table 13",
    "type": "rectangle-inverted",
    "seats": 2,
    "members": [
      {
        "name": "Name 85",
        "seat": 1
      },
      {
        "name": "Name 86",
        "seat": 2
      }
    ],
    "left": "80px",
    "top": "1400px"
  },
  {
    "id": 14,
    "name": "Table 14",
    "type": "rectangle-inverted",
    "seats": 4,
    "members": [
      {
        "name": "Name 87",
        "seat": 1
      },
      {
        "name": "Name 88",
        "seat": 2
      },
      {
        "name": "Name 89",
        "seat": 3
      },
      {
        "name": "Name 90",
        "seat": 4
      }
    ],
    "left": "300px",
    "top": "1400px"
  },
  {
    "id": 15,
    "name": "Table 15",
    "type": "rectangle-inverted",
    "seats": 6,
    "members": [
      {
        "name": "Name 91",
        "seat": 1
      },
      {
        "name": "Name 92",
        "seat": 2
      },
      {
        "name": "Name 93",
        "seat": 3
      },
      {
        "name": "Name 94",
        "seat": 4
      },
      {
        "name": "Name 95",
        "seat": 5
      },
      {
        "name": "Name 96",
        "seat": 6
      }
    ],
    "left": "530px",
    "top": "1400px"
  },
  {
    "id": 16,
    "name": "Table 16",
    "type": "rectangle-inverted",
    "seats": 8,
    "members": [
      {
        "name": "Name 97",
        "seat": 1
      },
      {
        "name": "Name 98",
        "seat": 2
      },
      {
        "name": "Name 99",
        "seat": 3
      },
      {
        "name": "Name 100",
        "seat": 4
      },
      {
        "name": "Name 101",
        "seat": 5
      },
      {
        "name": "Name 102",
        "seat": 6
      },
      {
        "name": "Name 103",
        "seat": 7
      },
      {
        "name": "Name 104",
        "seat": 8
      }
    ],
    "left": "790px",
    "top": "1400px"
  },
  {
    "id": 17,
    "name": "Table 17",
    "type": "rectangle-inverted",
    "seats": 10,
    "members": [
      {
        "name": "Name 105",
        "seat": 1
      },
      {
        "name": "Name 106",
        "seat": 2
      },
      {
        "name": "Name 107",
        "seat": 3
      },
      {
        "name": "Name 108",
        "seat": 4
      },
      {
        "name": "Name 109",
        "seat": 5
      },
      {
        "name": "Name 110",
        "seat": 6
      },
      {
        "name": "Name 111",
        "seat": 7
      },
      {
        "name": "Name 112",
        "seat": 8
      },
      {
        "name": "Name 113",
        "seat": 9
      },
      {
        "name": "Name 114",
        "seat": 10
      }
    ],
    "left": "80px",
    "top": "1750px"
  },
  {
    "id": 18,
    "name": "Table 18",
    "type": "rectangle-inverted",
    "seats": 12,
    "members": [
      {
        "name": "Name 115",
        "seat": 1
      },
      {
        "name": "Name 116",
        "seat": 2
      },
      {
        "name": "Name 117",
        "seat": 3
      },
      {
        "name": "Name 118",
        "seat": 4
      },
      {
        "name": "Name 119",
        "seat": 5
      },
      {
        "name": "Name 120",
        "seat": 6
      },
      {
        "name": "Name 121",
        "seat": 7
      },
      {
        "name": "Name 122",
        "seat": 8
      },
      {
        "name": "Name 123",
        "seat": 9
      },
      {
        "name": "Name 124",
        "seat": 10
      },
      {
        "name": "Name 125",
        "seat": 11
      },
      {
        "name": "Name 126",
        "seat": 12
      }
    ],
    "left": "340px",
    "top": "1750px"
  },
  {
    "id": 19,
    "name": "Table 19",
    "type": "circle",
    "seats": 2,
    "members": [
      {
        "name": "Name 127",
        "seat": 1
      },
      {
        "name": "Name 128",
        "seat": 2
      }
    ],
    "left": "80px",
    "top": "2300px"
  },
  {
    "id": 20,
    "name": "Table 20",
    "type": "circle",
    "seats": 4,
    "members": [
      {
        "name": "Name 129",
        "seat": 1
      },
      {
        "name": "Name 130",
        "seat": 2
      },
      {
        "name": "Name 131",
        "seat": 3
      },
      {
        "name": "Name 132",
        "seat": 4
      }
    ],
    "left": "280px",
    "top": "2300px"
  },
  {
    "id": 21,
    "name": "Table 21",
    "type": "circle",
    "seats": 6,
    "members": [
      {
        "name": "Name 133",
        "seat": 1
      },
      {
        "name": "Name 134",
        "seat": 2
      },
      {
        "name": "Name 135",
        "seat": 3
      },
      {
        "name": "Name 136",
        "seat": 4
      },
      {
        "name": "Name 137",
        "seat": 5
      },
      {
        "name": "Name 138",
        "seat": 6
      }
    ],
    "left": "500px",
    "top": "2300px"
  },
  {
    "id": 22,
    "name": "Table 22",
    "type": "circle",
    "seats": 8,
    "members": [
      {
        "name": "Name 139",
        "seat": 1
      },
      {
        "name": "Name 140",
        "seat": 2
      },
      {
        "name": "Name 141",
        "seat": 3
      },
      {
        "name": "Name 142",
        "seat": 4
      },
      {
        "name": "Name 143",
        "seat": 5
      },
      {
        "name": "Name 144",
        "seat": 6
      },
      {
        "name": "Name 145",
        "seat": 7
      },
      {
        "name": "Name 146",
        "seat": 8
      }
    ],
    "left": "820px",
    "top": "2300px"
  },
  {
    "id": 23,
    "name": "Table 23",
    "type": "circle",
    "seats": 10,
    "members": [
      {
        "name": "Name 147",
        "seat": 1
      },
      {
        "name": "Name 148",
        "seat": 2
      },
      {
        "name": "Name 149",
        "seat": 3
      },
      {
        "name": "Name 150",
        "seat": 4
      },
      {
        "name": "Name 151",
        "seat": 5
      },
      {
        "name": "Name 152",
        "seat": 6
      },
      {
        "name": "Name 153",
        "seat": 7
      },
      {
        "name": "Name 154",
        "seat": 8
      },
      {
        "name": "Name 155",
        "seat": 9
      },
      {
        "name": "Name 156",
        "seat": 10
      }
    ],
    "left": "80px",
    "top": "2600px"
  },
  {
    "id": 24,
    "name": "Table 24",
    "type": "circle",
    "seats": 12,
    "members": [
      {
        "name": "Name 157",
        "seat": 1
      },
      {
        "name": "Name 158",
        "seat": 2
      },
      {
        "name": "Name 159",
        "seat": 3
      },
      {
        "name": "Name 160",
        "seat": 4
      },
      {
        "name": "Name 161",
        "seat": 5
      },
      {
        "name": "Name 162",
        "seat": 6
      },
      {
        "name": "Name 163",
        "seat": 7
      },
      {
        "name": "Name 164",
        "seat": 8
      },
      {
        "name": "Name 165",
        "seat": 9
      },
      {
        "name": "Name 166",
        "seat": 10
      },
      {
        "name": "Name 167",
        "seat": 11
      },
      {
        "name": "Name 168",
        "seat": 12
      }
    ],
    "left": "450px",
    "top": "2600px"
  }
])

import Table from "./Table.vue";
import {ref, onMounted} from "vue";

const seats = {
  'square': 2,
  'circle': 2,
  'rectangle': 2
}

defineProps({
  size: Object
})


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

        // table.left = x + 'px'
        // table.top = y + 'px'
        event.target.style.transform =
            `translate(${x}px, ${y}px)`
        target.setAttribute('data-x', x);
        target.setAttribute('data-y', y);
        // emit('table-updated', props.details)
      },
    }
    //})
  })

})


const addTable = (type) => {

  let new_table = {
    "id": tables.value.length + 2,
    "name": "",
    "type": type,
    "seats": seats[type],
    "members": [],
    "left": "230px",
    "top": "100px"
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
</script>

<template>
  <div>
    <div class="toolbar">
      <div class="row">
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
      <Table @tableUpdated="updateTable" :id="'table_'+index"
             v-for="(table, index) in tables"
             :details="table" :key="index"/>
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