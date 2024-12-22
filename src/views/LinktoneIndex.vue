<template>
  <div class="linktone-index">
    <div class="genre-wrapper">
      <Genre />
    </div>
    <h2>לינקטונים</h2>
    <LinktoneList :linktones="linktones" @open-details="handleOpenDetails" />
    <div v-if="selectedLinktone" class="details-overlay" @click="closeDetails"></div>
          <Transition name="slide">
            <div
              v-if="selectedLinktone"
              class="details-container"
            >
            <LinktoneDetails :linktone="selectedLinktone" @close="closeDetails"/>
            </div>
          </Transition>
  </div>
</template>

<script>
import { linktones, linktoneService } from '@/services/LinktoneService'
import LinktoneList from '../components/LinktoneList.vue'
import Genre from '@/components/Genre.vue';
import LinktoneDetails from '@/components/LinktoneDetails.vue';

export default {
  name: 'LinktoneIndex',
  components: {
    LinktoneList,
    Genre,
    LinktoneDetails
  },
  emit: ['open-details'],
  data() {
    return {
      linktones: [],
      selectedLinktone: null,
    }
  },
  created() {
    this.loadLinktones()
  },
  methods: {
    async loadLinktones() {
      try {
        this.linktones = await linktoneService.getLinktones()
      } catch (error) {
        this.error = 'Error load linktone:' + error.message
      }
    },
    handleOpenDetails(linktone) {
      this.selectedLinktone = linktone
    },
    closeDetails() {
      this.selectedLinktone = null
    }
  },
}
</script>

<style lang="scss">
.linktone-index {
  display: flex;
  flex-direction: column;
  flex: 1;
  background-color:#fff;
  gap: 16px;
  width: 100%;
  position: relative;

  .genre-wrapper { width: 100%; display: flex; justify-content: flex-start;}
  h2 {padding-right: 30px;}
    .details-overlay { position:fixed; inset: 0; background: rgba(0, 0, 0, 0.5); z-index: 1;}
      .details-container { position: fixed; left: 0; top: 0;height: 100vh; width: 40%; z-index: 2;}
        .slide-enter-active,
        .slide-leave-active {transition: transform 0.3s ease;}
        .slide-enter-from,
        .slide-leave-to {transform: translateX(-100%);}
  }
</style>

