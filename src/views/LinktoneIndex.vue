<template>
  <div class="linktone-index">
    <h2>לינקטונים</h2>
    <LinktoneList :linktones="linktones" />
  </div>
</template>

<script>
import { linktoneService } from '@/services/LinktoneService'
import LinktoneList from '../components/LinktoneList.vue'

export default {
  name: 'LinktoneIndex',
  components: {
    LinktoneList,
  },
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
  },
}
</script>

<style lang="scss">
.linktone-index {
  width: 100%;
  display: flex;
  flex-direction: column;
  background-color:#fff;
  gap: 16px;

  h2 {
    padding-right: 30px;
  }
}
</style>
