<template>
  <nav class="sidebar">

    <div class="logo">
      <img src="../assets/linktone_img.jpg" />
    </div>

    <div class="actions">
      <div class="btn-container">
        <button class="btn" :class="{ active: mode === 'light' }" @click="toggleMode('light')">בהיר</button>
        <button class="btn" :class="{ active: mode === 'dark' }" @click="toggleMode('dark')">כהה</button>
      </div>
    </div>

    <ul class="list-items">
      <div class="list-item-container">
        <span class="icon">
          <i class="fa-solid fa-house"></i>
        </span>
        <li class="list-item">ראשי</li>
      </div>
      <div class="list-item-container">
        <span class="icon">
          <i class="fa-solid fa-headphones"></i>
        </span>
        <li class="list-item">בשבילך</li>
      </div>
      <div class="list-item-container">
        <span class="icon">
          <i class="fa-solid fa-circle-notch"></i>
        </span>
        <li class="list-item">לינקיפדיה</li>
      </div>
      <div class="list-item-container">
        <span class="icon">
          <i class="fa-solid fa-music"></i>
        </span>
        <li class="list-item">המצעד</li>
      </div>
      <div class="list-item-container">
        <span class="icon">
          <i class="fa-solid fa-comment"></i>
        </span>
        <li class="list-item">הודעות</li>
      </div>
      <div class="list-item-container">
        <span class="icon">
          <i class="fa-solid fa-sliders"></i>
        </span>
        <li class="list-item">הגדרות</li>
      </div>
    </ul>

    <div class="playlist-container">
      <h4>הפלייליסטים שלי</h4>
      <ul class="playlist-items">
        <li class="playlist-item">פותחים שבוע</li>
        <li class="playlist-item">שישי רגוע</li>
        <li class="playlist-item">אהבתי</li>
      </ul>
    </div>
  </nav>

  <nav class="mobile-navbar" :class="(modelValue ? '' : 'closed')">
    <span class="icon" @click="$emit('update:modelValue', false)">
      <i class="fa-solid fa-x"></i>
    </span>
      <ul class="mobile-list">
        <li class="mobile-list-item">ראשי</li>
        <li class="mobile-list-item">בשבילך</li>
        <li class="mobile-list-item">לינקיפדיה</li>
        <li class="mobile-list-item">המצעד</li>
        <li class="mobile-list-item">הודעות</li>
        <li class="mobile-list-item">הגדרות</li>
      </ul>
  </nav>
</template>

<script>
export default {
  name: 'Sidebar',
  props: ['modelValue'],
  emits: ['update:modelValue'],
  data() {
    return {
      mode: 'light'
    }
  },
      methods: {
      toggleMode(selectMode) {
        this.mode = selectMode
      }
    }
  }
</script>

<style lang="scss">
.sidebar {
  display: flex;
  flex-direction: column;
  font-size: 14px;
  width: 300px;
  height: 100vh;
  background-color: #1e212a;
  color: #fff;
  gap: 20px;


  .logo {
    display: flex;
    justify-content: center;
    img {
      width: 180px;
      height: 111px;
    }
  }

  .actions {
    display: flex;
    justify-content: center;

    .btn-container {
      border: 1px solid #fff;
      padding-inline: 5px;
      border-radius: 20px;
      
      .btn {
        border: none;
        background: none;
        padding-inline: 5px;
        color:#fff;
        cursor: pointer;
        transition: all 0.3s ease;

        &.active {
          background-color: #fff;
          color:#1e212a;
          border-radius: 20px;
          padding-inline: 10px;
          font-weight: 700;
        }
      } 
    }
  }

  .list-items {
    display: flex;
    flex-direction: column;
    list-style: none;

    .list-item-container {
      display: flex;
      align-items: center;
      padding: 12px 20px 12px 20px;
      gap: 5px;
      .icon {
        display: flex;
        align-items: center;
        color: #fff;
      }
    }
    .list-item {
      padding-inline: 10px;
      font-size: 20px;
      cursor: pointer;
    }
  }

  .playlist-container {
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding: 20px;

    h4 {
      font-size: 20px;
    }

    .playlist-items {
      display: flex;
      flex-direction: column;
      padding-inline: 20px;

      .playlist-item {
        font-size: 16px;
        padding: 3px;
      }
    }
  }

  @media (max-width: 600px) {
    display: none;
  }
}

@media(min-width: 601px) {
  .mobile-navbar {
    display: none;
  }
}

@media (max-width: 600px) {
  .mobile-navbar {
    position: fixed;
    background-color: #fff;
    width: 70%;
    height: 100%;
    z-index: 2;
    transition: 0.3s ease-in-out;


    &.closed {
      opacity: 0;height: 0;width: 0;
      transition: 0.3s ease-in-out;

    }

    .mobile-list {
      list-style: none;
      padding: 20px;
      opacity: 0.6;

      .mobile-list-item {
        padding: 10px;
        border-bottom: 1px solid lightgrey;
      }
    }

    .icon {
      display: flex;
      justify-content: flex-end;
      padding: 10px;
    }
  }
}

</style>
