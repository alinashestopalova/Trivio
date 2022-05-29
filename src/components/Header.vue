<template>
  <div class="header">
    <div class="logo">
      <img alt="Trivio logo" src="../assets/logo-trivio.svg">
    </div>
    <nav class="header_item menu-items">
      <ul>
        <li>Главная</li>
        <li>О компании</li>
        <li>Блог</li>
        <li>Контакты</li>
      </ul>
    </nav>
    <div class="header_item icons">
      <font-awesome-icon v-for="icon in icons"
                         :key="icon.name"
                         class="icon"
                         :icon="['fa-solid', icon.name]"
                         :style="{ color: icon.color }"
                         />
      <button class="user_profile_btn">aa</button>
      <div class="user_profile">
        <span>{{ user.name }}</span>
        <span class="user_finance">Тривио</span>
        <span class="user_finance">баланс: {{ user.balance }} &#8381;</span>
        <span class="user_finance">задолженность: {{ user.debt }} &#8381;</span>
        <span>Профиль</span>
        <span>Управление</span>
        <span>Моя компания</span>
        <span>Выйти</span>
      </div>
      <img src="../assets/lang-russia.svg" class="icon" alt="Language flag">
    </div>
  </div>
</template>

<script>
export default {
  name: 'TrivioHeader',
  data() {
    return {
      user: {
        name: "admin admin",
        balance: -597771.77,
        debt: 0.0,
      },
      icons: [
        {name: "search", color: '#8CC0DE'},
        {name: "clock", color: '#799351'},
        {name: "heart", color: '#F4BFBF'},
        {name: "pencil", color: '#0C1E7F'},
        {name: "envolope", color: '#DFD8CA'},
      ],
    }
  }
}
</script>

<style lang="scss">
.header {
  display: flex;
  align-content: center;
  padding: 10px;
  background: #fff;
  border-radius: 20px;

  .logo {
    display: flex;

    img {
      max-width: 100px;
      width: 100px;
      min-width: 100px;
      margin: auto;
      padding-left: 10px;
      display: block;
    }
  }

  .menu-items {
    display: flex;
    flex-grow: 1;
    align-items: center;
    justify-content: space-between;
    flex-wrap: nowrap;

    ul {
      display: flex;
      flex-wrap: nowrap;
    }

    li {
      display: inline-block;
      margin-right: 30px;
    }
  }

  .icons {
    display: flex;
    align-items: center;
    justify-content: flex-end;

    .icon {
      margin: 0 10px;
      height: 18px;
      width: 18px;
    }

    .user_profile_btn {
      color: blue;
      margin: 0 10px;
      background: #C4DDFF;
      padding: 8px 10px;
      border-radius: 8px;
      border-width: 0px;
      transition: 2s;

      &:focus {
        pointer-events: none;
      }
    }

    .user_profile {
      border-radius: 10px;
      display: none;
      padding: 20px;
      position: absolute;
      background: #fff;
      height: 150px;
      width: 150px;
      top: 85px;
      right: 30px;
      font-size: 12px;

      span {
        margin: 4px 0;
      }

      span:last-child {
        margin-top: 15px;
      }

      .user_finance {
        font-size: 10px;
        color: #d1d1d1;
        margin: 0;
      }
    }
  }

  @media screen and (max-width: 830px) {
    .menu-items {
      font-size: 14px;
    }

  }

  @media screen and (max-width: 768px) {
    flex-direction: column;

    .header_item {
      justify-content: center;

      .user_profile {
        top: 140px;
        right: calc(50% - 85px);
      }
    }
  }

  .user_profile_btn:focus + .user_profile  {
    display: flex;
    flex-direction: column;
  }

}
</style>