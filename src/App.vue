<script setup>
import { RouterView } from 'vue-router'
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
import Genre from './components/Genre.vue';
</script>

<template>
  <div class="app">
      <Sidebar />
    <div class="content">
      <div class="sidebar-container">
        <Header />
      </div>
      <div class="genre-container">
        <Genre />
      </div>
      <div class="main-container">
        <main class="main">
          <RouterView /> 
        </main>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  .app {
    display: flex;
    font-family: "Poppins", sans-serif;
    overflow: hidden;
    height: 100vh;
    .content { flex: 1; display: flex; flex-direction: column; gap: 82px; background-color: #fff;}
    .main-container {
      width: 100%;
      padding: 20px;
    }
    .sidebar-container {
      background-color: #1e212a;
    }

    .genre-container {
      height: 10vh;
    }
    main { flex: 1; display: flex; justify-content: center; width: 100%;} 
  }

</style>
