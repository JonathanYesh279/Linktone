<script setup>
import { RouterView } from 'vue-router'
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
</script>

<template>
  <div class="page_wrap" :class="(nav ? 'nav-open' : 'nav-closed')">
    <Sidebar :model-value="nav" @update:model-value="newValue => nav = newValue" />
    <div class="content">
      <Header :model-value="nav" @update:model-value="newValue => nav = newValue" />
      <div class="main-container">
        <main class="main">
          <RouterView /> 
        </main>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      nav: false,
    }
  },
  methods: {
  }
}
</script>


<style scoped lang="scss">
  .page_wrap { display: flex; font-family: "Poppins", sans-serif; overflow: hidden; height: 100vh; position: relative;
    .content { flex: 1; display: flex; flex-direction: column; gap: 20px; background-color: #fff;}
    .main-container { width: 100%; padding: 20px; display: flex; flex-direction: column; gap: 20px; position: relative;
      .details-overlay { position: fixed; inset: 0;background: rgba(0, 0 ,0, 0.5); z-index: 1;}
    .sidebar-container {
      background-color: #1e212a;
    }
  }

    main { flex: 1; display: flex; justify-content: center; width: 100%;} 
  }

</style>
