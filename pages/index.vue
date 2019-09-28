<template>
  <div class="container">
    <header>
      <div class="top-nav">
        <div class="top-left">
          <img class="menu" src="menu-icon.png" alt="">
          <img class="logo" src="RH-Logo-Grey.svg" alt="">
        </div>
        <div class="top-right">
          <a href="">shop rooms</a>
          <img class="search" src="search-icon.png" alt="">
          <a href="">sign in</a>
          <a href="">cart 0</a>
        </div>
      </div>
      <div class="bottom-nav">
        <a href="">Living</a>
        <a href="">Dinning</a>
        <a href="">Bed</a>
        <a href="">Bath</a>
        <a href="">Lighting</a>
        <a href="">Textiles</a>
        <a href="">Rugs</a>
        <a href="">Windows</a>
        <a href="">Hardware</a>
        <a href="">DÉCOR</a>
        <a href="">Art</a>
        <a href="">Outdoor</a>
        <a style="font-weight: 700;" href="">Sale</a>
      </div>
    </header>
  </div>
</template>

<script>

export default {

}
</script>

<style>
  .container {
    background-color: black;
    height: 100vh;
  }
  header {
    margin: 0 auto;
    padding-top: 25px;
    max-width: 1240px;
    min-width: 1000px;
    height: 125px;
  }
  .top-nav {
    display: flex;
    justify-content: space-between;
    padding-bottom: 10px;
    border-bottom: 1px solid rgba(255,255,255,0.4);
  }
  .top-left, .top-right {
    display: flex;
    align-items: center;
  }
  .top-right a {
    padding: 0 10px;
    font-weight: 300;
  }
  .bottom-nav {
    display: flex;
    justify-content: space-between;
  }
  header a {
    color: white;
    font-weight: 500;
    font-size: 10px;
    line-height: 30px;
    letter-spacing: .15em;
    text-transform: uppercase;
  }
  .logo {
    height: 29px;
    width: 46px;
    margin-left: -4px;
  }
  .menu {
    width: 27.5px;
    height: 17.5px;
    padding-right: 15px
  }
  .search {
    width: 15px;
    height: 15px;
    padding: 0 10px;
  }
</style>
