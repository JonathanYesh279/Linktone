<template>
  <div class="linktones_con">
    <ul class="linktone-list">
      <li v-for="linktone in linktones" 
          :key="linktone.id" 
          @click="handleClick(linktone)">
        <linktone-preview :linktone="linktone" />
      </li>
    </ul>
  </div>
</template>

<script>
import LinktonePreview from './LinktonePreview.vue'

export default {
  name: 'LinktoneList',
  components: {
    LinktonePreview,
  },
  props: {
    linktones: {
      type: Array,
      required: true,
    },
  },
  emits: ['open-details'],
  methods: {
    handleClick(linktone) {
      this.$emit('open-details', linktone)
    }
  }
}
</script>

<style lang="scss" scoped>
.linktones_con { flex: 1; padding: 0 20px; }
.linktone-list {
  &::-webkit-scrollbar {
    width: 6px;
  }
  &::-webkit-scrollbar-track {
    background: #fff; 
  } 
  &::-webkit-scrollbar-thumb {
    background: #333;
    border-radius: 10px;
  }

  display: grid;
  // width: 1260px;
  grid-template-columns: repeat(5, 1fr);
  gap: 60px 20px;
  list-style: none;
  overflow: auto;
  max-height: 720px;
  padding-right: 20px;
  padding-left: 50px;
  direction: ltr;
  width: 100%;
  @media (max-width: 1540px) { 
      grid-template-columns: repeat(4, 1fr);

  }

  @media (max-width: 1220px) {
    grid-template-columns: repeat(3,  1fr);
    padding-left: 150px;
    
    }
  
  @media (max-width: 1130px) {
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    padding-left: 200px;
  }

  @media (max-width: 800px) {
    grid-template-columns: repeat(1, 1fr);
    gap: 20px;
    padding-right:10px;
    padding-left: 0;
  }

  @media (max-width: 600px) {
    grid-template-columns: repeat(1, 1fr);
    gap: 30px;
    padding-right: 10px;
    padding-left: 0;
  }

  li {direction: rtl; width: 100%; height: auto; aspect-ratio: 1;}
}


</style>
