<template>
  <nav class="navbar">
      <ul class="nav-lists">
        <div class="catalog">
          <span> קטלוג </span>
          <i class="fa-solid fa-chevron-left"></i>
        </div>
        <li class="nav-list">הכל</li>
        <li class="nav-list active">סגנון מוזיקלי</li>
        <li class="nav-list">סינגלים</li>
        <li class="nav-list">אלבומים</li>
        <li class="nav-list">קליפים</li>
        <li class="nav-list">לייבלים</li>
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

<style scoped lang="scss">
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-inline: 20px;
  width: 100%;
  height: 75px;
  border-bottom: 1px solid #adadad;
  background-color: #fff;
  border-top-right-radius: 20px;
  gap: 10px;

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
  & { display: flex; list-style: none; background-color: #fff; gap: 35px; }
  @media (max-width: 600px) { }
  @media (min-width: 600px) { }
  .nav-list {
    & { display: flex; height: 22px; cursor: pointer; }
    &.active { background-image: linear-gradient(red, blue); color: transparent; background-clip: text; }
  }

  .icon {
    cursor: pointer;
  }
}

.inputs-container {
  display: flex;
  gap: 10px;

  input {
    padding: 5px 5px;
    border-radius: 20px;
    border: 1px solid #999;
  }
}

.user-info-contianer {
  display: flex;
  align-items: center;
  gap: 10px;

  .icon {
    width: 22px;
    height: 22px;
    cursor: pointer;
  }

  .avatar {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: blueviolet;
    color: #fff;
    border-radius: 50%;
    width: 53px;
    height: 53px;
    cursor: pointer;
  }

  .user-info {
    p {
      font-size: 12px;
      line-height: 1;
    }

    div {
      padding-inline: 5px;
      color: #fff;
      background-color: #ff1661;
      border-radius: 10px;
      font-size: 10px;
    }
  }
}
</style>
