<script setup>
  import Table from "./Table.vue";

  defineProps({
    size: Object
  })


  const tableStyle = {seats: 4, type: 'square', left: '100px', top: '100px'};

</script>

<template>
  <div class="room">
    <Table :style="tableStyle"/>
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

</style>