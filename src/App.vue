<script setup>
import Room from './components/Room.vue';

const roomSize = {width: '1200px', height: '3000px'};


</script>

<template>
  <Room :size="roomSize"/>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>