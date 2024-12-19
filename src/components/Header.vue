<template>
  <nav class="navbar">
      <ul class="nav-lists">
        <div class="catalog">
          <span> קטלוג </span>
          <i class="fa-solid fa-chevron-left"></i>
        </div>

        <div class="mobile-menu" @click="$emit('update:modelValue', true)">
          <i class="fa-solid fa-bars"></i>
        </div>
  
        <li class="nav-list" :key="activeLink.name" @click="activeLink.active =! activeLink.active" v-for="activeLink in activeLinks" v-text="activeLink.name" :class="{ active: activeLink.active }" ></li>
        <span class="icon">
          <i class="fa-solid fa-ellipsis-vertical"></i>
        </span>
      </ul>

      <div class="inputs-container">
        <input type="date" placeholder="13.05.2020" />
        <input type="text" placeholder="חיפוש אמנים" />
      </div>

      <div class="user-info-contianer">
        <span class="icon">
          <i class="fa-regular fa-bell fa-lg"></i>
        </span>
        <div class="avatar">YY</div>
        <div class="user-info">
          <p>בוקר טוב</p>
          <span>יונתן ישעיהו</span>
          <div>תאגיד השידור הישראלי</div>
        </div>
      </div>
  </nav>
</template>

<script>
export default {
  name: 'Header',
  props: ['modelValue'],
  emits: ['update:modelValue'],
  data() {
    return { 
      activeLinks: [
          {name: 'הכל', active: false},
          {name: 'סגנון מוזיקלי', active: false},
          {name: 'סינגלים', active: false},
          {name: 'אלבומים', active: false},
          {name: 'קליפים', active: false},
          {name: 'לייבלים', active: false}
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-inline: 20px;
  font-size: 18px;
  width: 100%;
  height: 75px;
  border-bottom: 1px solid #adadad;
  background-color: #fff;
  border-top-right-radius: 20px;
  gap: 10px;

  @media (max-width: 600px) {
    border-top-right-radius: 0px;
  }

  .catalog {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  span {
    font-weight: 700;
  }
}

.nav-lists {
  & { display: flex; list-style: none; background-color: #fff; gap: 35px; 
    .mobile-menu {display: none;}
  @media (max-width: 600px) {
    .catalog {display: none;}
    .mobile-menu {
      font-size: 22px;
      display: flex;
      align-items: center;
    }
  }
  }

  .nav-list {
    & { display: flex; height: 22px; cursor: pointer; }
    &.active { background-image: linear-gradient(red, blue); color: transparent; background-clip: text; font-weight: 700; }
    @media (max-width: 600px) {display: none;}
  }

  .icon {cursor: pointer;
  @media (max-width: 600px) {
    display: none;
  }
  }

}

.inputs-container {display: flex; gap: 10px;

  input {padding: 5px 5px; border-radius: 20px; border: 1px solid #999;}

  @media (max-width: 600px) {
    display:none;
  }
}

.user-info-contianer {display: flex; align-items: center; gap: 10px; padding:10px 0px;
  .icon {width: 22px; height: 22px; cursor: pointer;}
  .avatar {display: flex; justify-content: center; align-items: center; background-color: blueviolet; color: #fff; border-radius: 50%; width: 53px; height: 53px; cursor: pointer;}
  .user-info {
    p {font-size: 12px; line-height: 1;}
    div {padding-inline: 5px; color: #fff; background-color: #ff1661; border-radius: 10px; font-size: 10px;}
    @media (max-width: 600px) {
      span {font-size: 14px;}
      div {padding-inline: 2px;}
    }
  }
  @media (max-width: 600px) {
    .user-info-container {

      .icon {width: 30px; height: 30px;}
    }
    .avatar {width: 30px; height: 30px;}
  }
}
</style>
