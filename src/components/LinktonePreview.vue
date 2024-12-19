<template>
  <div class="linktone-preview">
    <div class="content-preview">
      <h3>גל אדם</h3>
      <p>איתך עושה לי טוב</p>
      <p class="date">20.05.2024</p>
      <div class="btn"></div>
      <div class="play-container">
       <div class="play">
         <span><i class="fa-solid fa-play"></i></span>
       </div>
     </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LinktonePreview',
  props: {
    linktone: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style scoped lang="scss">
.linktone-preview {
  display: flex;
  position: relative;
  align-items: flex-end;
  border-radius: 14px;
  color: #fff;
  width: 100%;
  height: 100%;
  box-shadow: 0 3px 6px 0 rgba(0, 0, 0, 0.23);
  background-image: url('../src/assets/linktone_image.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  cursor: pointer;

  &:after {
    content: '';
    position: absolute;
    border-radius: 14px;
    inset: 0;
    z-index: 0;
    background: linear-gradient(transparent 70%, black);
  }
  }



.content-preview {
  display: flex;
  align-items: flex-start;
  padding: 10px;
  font-size:22px;
  flex-direction: column;
  width: 100%;
  z-index: 1;

  h3 {
    font-size: 24px;
    line-height: 1;
  }

  p:nth-child(2) {
    font-size: 18px;
    font-weight: 300;
    line-height: 1;
  }

  p:nth-child(3) {
    opacity: 0.7;
  }

  .date {
    font-size: 12px;
    color: rgb(255, 251, 251);
  }

  @media(max-width: 600px) {
    h3 {
      font-size: 14px;
    }
    p:nth-child(2) {
      font-size: 10px;
    }
    p:nth-child(3) {
      font-size: 6px;
    }
  }
}

.play-container {
  position: absolute;
  bottom: -20px;
  left: 20px;

  @media (max-width: 600px) {
    left: 10px;
  }
}
.play {
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #ff1661 13%, #00b7ff 123%);
  border-radius: 50%;
  width: 50px;
  height: 50px;
}
</style>
