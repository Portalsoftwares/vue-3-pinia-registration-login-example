<script setup>
import { useAuthStore } from "@/stores";

const authStore = useAuthStore();
</script>
<!-- 
<template>
    <nav v-show="authStore.user" class="navbar navbar-expand navbar-dark bg-dark">
        <div class="navbar-nav">
            <router-link to="/" class="nav-item nav-link">Home</router-link>
            <router-link to="/users" class="nav-item nav-link">Users</router-link>
            <button @click="authStore.logout()" class="btn btn-link nav-item nav-link">Logout</button>
        </div>
    </nav>
</template> -->

<template>
  <nav v-show="authStore.user" class="navbar navbar-expand navbar-dark bg-dark">
    <div class="navbar-nav">
      <router-link to="/" class="nav-item nav-link order-1">Home</router-link>
    </div>

    <div class="navbar-nav ml-auto">
      <span class="ispan"> {{ authStore.user.firstName }} </span>
      <router-link to="/users" class="nav-item nav-link">Users</router-link>

      <button
        @click="authStore.logout()"
        class="btn btn-link nav-item nav-link text-white logout-btn"
      >
        Logout
      </button>
    </div>
  </nav>
</template>

<style>
.logout-btn:hover {
  font-weight: bold;
  font-size: 1.5em; /* aumenta o tamanho em 50% */
}
.nav-item:hover {
  text-align: center;
}
.ispan{
  font-size: 1.5em;
  font-weight: bold;
  color: white;
  margin-right: 10px;

}
</style>
