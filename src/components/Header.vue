<script setup>

import { ref } from 'vue';
const title = ref('Historeo');

const signIn = () => {
  alert('Sign In');
};
const signUp = () => {
  alert('Sign Up');
};

const menus = ref({
  homeMenu: false,
  historyMenu: false,
  gamesMenu: false,
  alexanderMenu: false,
});

const toggleMenu = (menuKey) => {
  // Close all menus
  Object.keys(menus).forEach(key => {
    menus[key] = false;
  });

  // Toggle the clicked menu
  menus[menuKey] = !menus[menuKey];
  console.log("menuKey: ", menus[menuKey]);
};

</script>

<template>
  <header class="history-header">
    <div class="header-content">
      <h1 class="blog-title" v-text="title"></h1>
      <div class="auth-buttons">
        <button @click="signIn" class="sign-in">Sign In</button>
        <button @click="signUp" class="sign-up">Sign Up</button>
      </div>
    </div>
  </header>
  <div>
    <nav class="main-nav">
      <ul class="nav-links">
        <li class="nav-option">Home</li>
        <li class="nav-option">News</li>
        <li class="nav-option" @mouseenter="toggleMenu('gamesMenu')" @mouseleave="toggleMenu('gamesMenu')">Games
        <div class="dropdown-content" v-if="menus.gamesMenu">
          <a href="#">Europa Universalis 4</a>
          <a href="#">Hearts of Iron 4</a>
          <a href="#">Victoria 3 </a>
        </div>
        </li>
        <li class="nav-option">Olesti</li>
      </ul>
    </nav>
  </div>

</template>

<style lang="scss" scoped>
$background-color: #383838; // A shade of black
$header-background-color: navajowhite; // A shade of green
.history-header {
  background-color: $header-background-color;
  padding: 10px 20px;

  .header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 10px 22% auto;


    .blog-title {
      font-family: 'Times New Roman', serif; // Classic font for a historical feel
      font-size: 2em;
      white-space: nowrap;
      overflow: hidden;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
      color: $background-color;
      animation: fadeIn 1s ease-in-out 1; /* Apply the fadeIn animation */
    }

    .auth-buttons {
      display: flex;

      button {
        margin-left: 10px;
        padding: 5px 15px;
        cursor: pointer;
        border: none;
        color: $background-color;
        text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        //  background-color: #6d7f9d; // Adjust colors as needed
        font-size: 15px;
        border-radius: 5px;
        transition: background-color 0.3s;

        &:hover {
          opacity: 0.8;
        }
      }

      .sign-in {
        background-color: cadetblue;

        .sign-up {
          background-color: #31708e
        }
      }
    }
  }
}

.main-nav{
  display: flex;
  background-color: greenyellow;
  justify-content: center;
  align-items: center;
  margin:auto;

  ul {
    padding: 0;
    list-style: none;
    display: flex;

    .nav-option {
      margin: 0 15px;
      font-family: 'Times New Roman', serif;
      font-weight: bold;
      font-size: 1.2em;
      position: relative; /* For absolute positioning of dropdown */
      cursor: pointer;
      color: $background-color; /* Default color of the nav items */
    }
  }
  .dropdown-content {
    display: block;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    z-index: 1;

    a {
      color: black;
      padding: 12px 16px;
      text-decoration: none;
      display: block;
      &:hover {
        background-color: #f1f1f1;
      }
    }
  }

}
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
</style>