<script setup>
import { useRoute, useRouter } from "vue-router";
import { ref } from "vue";

const route = useRoute();
const router = useRouter();

const isLoggedIn = false;
const isLoginPage = router.currentRoute.value.name === "login";

const isAuthenticated = ref(false);

const login = () => {
  isAuthenticated.value = true;
};

const logout = () => {
  isAuthenticated.value = false;
};

const goToLogin = () => {
  router.push("/login");
};

const goToRegister = () => {
  router.push("/register");
};
</script>

<template>
  <header>
    <img src="../../assets/images/icons/logopandana.png" alt="" />

    <div class="buttons">
      <v-btn class="button1" color="#90ccd9 " @click="toggleAuth">
        {{ isLoggedIn ? "Cerrar Sesión" : "Iniciar Sesión" }}
      </v-btn>
      <v-btn
        class="button1"
        color="#90CCD9"
        v-if="isLoggedIn && !isLoginPage"
        @click="goToHome"
        >Home</v-btn
      >
      <v-btn class="button2" color="#90ccd9">registrarse</v-btn>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  background-color: #90ccd9;
  width: 100%;
  height: 150px;
  display: flex;
  justify-content: space-between;
}

.buttons {
  margin-top: 80px;
  margin-right: 50px;
}

.button1 {
  margin-right: 25px;
}
</style>
