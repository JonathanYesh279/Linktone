<template>
  <div class="linktones_con">
    <ul class="linktone-list">
      <li v-for="linktone in linktones" 
          :key="linktone.id" 
          @click="$emit('isDetailsOpen', linktone)">
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
}
</script>

<style lang="scss" scoped>
.linktones_con { flex: 1; }
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
  direction: ltr;
  @media (max-width: 1540px) { 
      grid-template-columns: repeat(4, 1fr);

  }

  @media (max-width: 1232px) {
    grid-template-columns: repeat(3, 1fr);
    }
  
  @media (max-width: 700px) {
    grid-template-columns: repeat(2, 1fr);
  }
  

  li {direction: rtl;
    aspect-ratio: 1;
  }
  
}


</style>
