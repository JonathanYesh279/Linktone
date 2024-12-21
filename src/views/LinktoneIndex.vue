<template>
  <div class="linktone-index">
    <div class="genre-wrapper">
      <Genre />
    </div>
    <h2>לינקטונים</h2>
    <LinktoneList :linktones="linktones" @open-details="handleOpenDetails" />
  </div>
</template>

<script>
import { linktones, linktoneService } from '@/services/LinktoneService'
import LinktoneList from '../components/LinktoneList.vue'
import Genre from '@/components/Genre.vue';

export default {
  name: 'LinktoneIndex',
  components: {
    LinktoneList,
    Genre
  },
  emit: ['open-details'],
  data() {
    return {
      linktones: [],
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
      this.$emit('open-details', linktone)
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

  .genre-wrapper { width: 100%; display: 100%; display: flex; justify-content: flex-start;}

  h2 {
    padding-right: 30px;
  }
}
</style>
