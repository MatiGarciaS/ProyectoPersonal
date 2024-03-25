<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import { useEventStore } from "@/stores/event";
import cardmenu from "@/components/cards/cardmenu.vue";
// import Carusel from "@/components/card/Carusel.vue";
</script>


const store = useEventStore()
store.getEvents()


 <template>

<!-- {/* <div> 
  <Carusel :events="store.events"/>
</div> */} -->

  <main>
<div v-for="event in store.events">
  <CardMenu :event="event" />
  
<!-- </div> -->

</main>
<main>
  <cardmenu />
</main>

</template>
<template>
  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>

main {
  display: flex;
  justify-content: space-around;
  margin: 5%;
  flex-wrap: wrap;
  gap:  10px; 
 
  border-radius: 15px;

}

@media (max-width:  768px) {
  .cardmenu {
    width:  100%;
  }
}
</style>