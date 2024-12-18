<template>
  <nav class="sidebar">

    <div class="logo">
      <img src="../assets/linktone_img.jpg" />
    </div>

    <div class="actions">
      <div class="btn-container">
        <button class="btn" @click="modeToggle">בהיר</button>
        <button class="btn" @click="modeToggle">כהה</button>
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
</template>

<script>
export default {
  name: "Sidebar",
  methods: {
    // toggleMode() {

    // }
  }
}
</script>

<style lang="scss">
.sidebar {
  display: flex;
  flex-direction: column;
  font-size: 14px;
  width: 212px;
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
    }
  }

  .playlist-container {
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding: 20px;

    .playlist-items {
      display: flex;
      flex-direction: column;
      padding-inline: 20px;

      .playlist-item {
        font-size: 0.8rem;
        padding: 3px;
      }
    }
  }
}
</style>
