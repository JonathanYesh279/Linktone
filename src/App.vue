<script setup>
import { RouterView } from 'vue-router'
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
import Genre from './components/Genre.vue';
import LinktoneDetails from './components/LinktoneDetails.vue';
</script>

<template>
  <div class="page_wrap" :class="(nav ? 'nav-open' : 'nav-closed')">
    <Sidebar :model-value="nav" @update:model-value="newValue => nav = newValue" />
    <div class="content">
      <Header :model-value="nav" @update:model-value="newValue => nav = newValue" />
      <div class="main-container">
        <main class="main">
          <RouterView @open-details="openDetails" /> 
          <div v-if="selectedLinktone" class="details-overlay" @click="closeDetails"></div>
          <Transition name="slide">
            <div
              v-if="selectedLinktone"
              class="details-container"
            >
            <LinktoneDetails :linktone="selectedLinktone" @close="closeDetails"/>
            </div>
          </Transition>
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
      selectedLinktone: null,
    }
  },
  methods: {
    openDetails(linktone) {
      this.selectedLinktone = linktone
    },
    closeDetails() {
      this.selectedLinktone = null
    }
  }
}
</script>


<style scoped lang="scss">
  .page_wrap { display: flex; font-family: "Poppins", sans-serif; overflow: hidden; height: 100vh; position: relative;
    .content { flex: 1; display: flex; flex-direction: column; gap: 20px; background-color: #fff;}
    .main-container { width: 100%; padding: 20px; display: flex; flex-direction: column; gap: 20px; position: relative;
      .details-overlay { position: fixed; inset: 0;background: rgba(0, 0 ,0, 0.5); z-index: 1;}
      .details-container { position: fixed; left: 0; top: 0;height: 100vh; width: 40%; z-index: 2;}
        .slide-enter-active,
        .slide-leave-active {transition: transform 0.3s ease;}
        .slide-enter-from,
        .slide-leave-to {transform: translateX(-100%);}
    .sidebar-container {
      background-color: #1e212a;
    }
  }

    main { flex: 1; display: flex; justify-content: center; width: 100%;} 
  }

</style>
