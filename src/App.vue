<!-- src/App.vue -->
<template>
  <div id="app">
    <Calendar />
  </div>
</template>

<script>
import Calendar from './components/calendar.vue';

export default {
  components: {
    Calendar
  }
};
</script>
<style>
#app{
  display: inline;
  background-color: gray;

}

.neww{
  display: none;
}
</style>
