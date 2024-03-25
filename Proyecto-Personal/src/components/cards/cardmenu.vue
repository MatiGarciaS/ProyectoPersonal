<script setup>

import { useRoute, useRouter } from "vue-router";

const route = useRoute()
const router = useRouter()

const props = defineProps({
    event: {
        type: Object,
        required: true,
    },

});

const goToLogin = () => {
  router.push('/login');
}

</script>

<template>

    <v-card
    class="mx-auto my-12" color="teal-lighten-5"
    max-width="250" :style="{ borderRadius: '15px', border: '2px solid blue', height: '500px'  }">
    
<v-img
cover
height="150"
width="300"
src="../../assets/images/ensalada1.jpeg"></v-img>

    <v-card-item class="prueba"> 
        <v-card-title>{{ menu.title }}</v-card-title>
    </v-card-item>

    <v-card-text>
        <div class="my-2 text-subtitle-1">{{ menu.date }}</div>
        <div>{{ menu.description }}</div>
    </v-card-text>

<!-- <div class="evento">
    <v-card-title>{{ event.place }}</v-card-title>
    <v-card-title>{{ event.hour }}</v-card-title>
</div> -->


<v-btn
color="125D6E" absolute :style="{ left: '50%', transform: 'translateX(-50%)', width: '100px', fontSize: 'x-small' }" class="mb-2" @click="goToLogin">Pedir
</v-btn>

</v-card>


</template>

<style scoped lang="scss">
    .prueba{
        padding: 0;
        margin-left: 5%;
    }
    .evento{
        display: flex;
        justify-content: space-between;
    }
</style>

</script>