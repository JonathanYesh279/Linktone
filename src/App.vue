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
        <Genre />
        <main class="main">
          <RouterView /> 
          <div class="details-container" :class="{ 'display-details': isDetailsOpen }">
          <LinktoneDetails 
            v-if="isDetailsOpen"
            @close="closeDetails" 
          />
        </div>
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
      isDetailsOpen: true,
    }
  },
  computed: {
    
  },
  methods: {
    
  }
}
</script>


<style scoped lang="scss">
  .page_wrap { display: flex; font-family: "Poppins", sans-serif; overflow: hidden; height: 100vh;
    .content { flex: 1; display: flex; flex-direction: column; gap: 20px; background-color: #fff;}
    .main-container { width: 100%; padding: 20px;
      .details-container { position: fixed; left: 0; top: 0;height: 100vh; width: 40%;
      &.display-details {position: fixed; display: flex; z-index: 2;}
      }
    }
    .sidebar-container {
      background-color: #1e212a;
    }

    main { flex: 1; display: flex; justify-content: center; width: 100%;} 
  }

</style>
