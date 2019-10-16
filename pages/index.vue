<template>
  <div class="container">
    <header>
      <div class="side-nav" id="sideNav" ref="sideNav">
        <div class="side-nav-title">
          <img src="rh-interiors.png" id="logo" ref="logo" alt="">
        </div>
        <div class="sub-nav" id="subNav1" ref="subNav1" style="padding-top: 100px;">
          <p class="sub-nav-title" style="padding-bottom: 20px;">THE PRODUCTS</p>
          <a href=""><p>INTERIORS / MODERN / OUTDOOR</p></a>
          <a href=""><p>BEACH HOUSE / SKI HOUSE / COLOR</p></a>
          <a href=""><p>BABY / CHILD / TEEN</p></a>
          <a href=""><p>WATERWORKS BATH & KITCHEN</p></a>
        </div>
        <div class="sub-nav" id="subNav2" ref="subNav2">
          <p class="sub-nav-title" style="padding-bottom: 20px;">THE PLACES</p>
          <a href=""><p>GALLERIES</p></a>
          <a href=""><p>GUESTHOUSES</p></a>
          <a href=""><p>RESTAURANTS</p></a>
          <a href=""><p>RESIDENCES</p></a>
        </div>
        <div class="sub-nav" id="subNav3" ref="subNav3" style="border-bottom: none;">
          <p class="sub-nav-title" style="padding-bottom: 20px;">THE SPACES & SERVICES</p>
          <a href=""><p>ARCHITECTURE</p></a>
          <a href=""><p>INTERIOR DESIGN</p></a>
          <a href=""><p>LANDSCAPE ARCHITECTURE</p></a>
          <a href=""><p>PLANE / YACHT DESIGN & CHARTER</p></a>
        </div>
      </div>
      <div class="top-nav">
        <div class="top-left">
          <!-- <img class="menu" src="menu-icon.png" alt=""> -->
          <button @click="showNav()" class="hamburger hamburger--squeeze" type="button">
            <span class="hamburger-box">
              <span class="hamburger-inner"></span>
            </span>
          </button>
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
        <a href="">Dining</a>
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
  data () {
    return {
      sideNavActive: false
    }
  },
  mounted () {
    var forEach=function(t,o,r){if("[object Object]"===Object.prototype.toString.call(t))for(var c in t)Object.prototype.hasOwnProperty.call(t,c)&&o.call(r,t[c],c,t);else for(var e=0,l=t.length;l>e;e++)o.call(r,t[e],e,t)};

    var hamburgers = document.querySelectorAll(".hamburger");
    if (hamburgers.length > 0) {
      forEach(hamburgers, function(hamburger) {
        hamburger.addEventListener("click", function() {
          this.classList.toggle("is-active");
        }, false);
      })
    }
  },
  methods: {
    showNav() {
      if (this.sideNavActive) {
          this.$refs.subNav3.style.opacity = 0
          this.$refs.subNav2.style.opacity = 0
          this.$refs.subNav1.style.opacity = 0
          this.$refs.logo.style.opacity = 0
        setTimeout(() => {
          this.$refs.sideNav.style.opacity = 0
          this.$refs.sideNav.style.width = '0px'
        }, 250)
      } else {
        this.$refs.sideNav.style.opacity = 1
        this.$refs.sideNav.style.width = '300px'
        setTimeout(() => {
          this.$refs.subNav1.style.opacity = 1
          this.$refs.subNav2.style.opacity = 1
          this.$refs.subNav3.style.opacity = 1
        }, 250)
        setTimeout(() => {
          this.$refs.logo.style.opacity = 1
        }, 350)
        // setTimeout(() => {
        //   this.$refs.subNav3.style.opacity = 1
        // }, 750)
      }
      this.sideNavActive = !this.sideNavActive
    }
  }
}
</script>

<style>
  .container {
    background: url('/bg.jpg');
    background-size: cover;
    background-position: center;
    height: 100vh;
  }
  header {
    margin: 0 auto;
    padding-top: 25px;
    width: 1060px;
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
    line-height: 10px
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
  .side-nav {
    transition: all .5s ease-in;
    width: 0;
    position: absolute;
    top: 0;
    left: 0;
    background: white;
    height: 100vh;
    opacity: 0;
    overflow-y: scroll;
  }
  .side-nav-title {
    padding: 34px 60px 0;
    position: fixed;
    background-color: white;
    width: 180px;
  }
  .side-nav img {
    width: 75%;
    /* top: 34px;
    left: 60px;
    padding-bottom: 75px;
    position: absolute; */
    opacity: 0;
    transition: all .5s ease-in;
  }

  .sub-nav {
    transition: all .5s ease-in;
    border-bottom: 1px solid #ccc;
    color: #333;
    width: 81%;
    margin: 0 auto;
    padding-top: 25px;
    opacity: 0;
  }
  .sub-nav-title {
    font-family: 'BaronSans-Roman', sans-serif;
    font-size: 6pt;
    letter-spacing: .1em;
    line-height: 6.67pt;
  }
  .sub-nav a > p {
    font-family: 'CaslonRH-Thin', sans-serif;
    font-size: 11pt;
    padding-top: 10px;
    letter-spacing: .08em;
    line-height: 13.67pt;
    color: #333;
    padding-bottom: 25px;
  }


/* Hamburger Style/Animation */
.hamburger {
  padding: 0 20px 0 0;
  display: inline-block;
  cursor: pointer;
  transition-property: opacity, filter;
  transition-duration: 0.15s;
  transition-timing-function: linear;
  font: inherit;
  color: inherit;
  text-transform: none;
  background-color: transparent;
  border: 0;
  margin: 0;
  overflow: visible; 
}
.hamburger:hover {
  opacity: 0.7; 
}
.hamburger.is-active:hover {
  opacity: 0.7; 
}
.hamburger.is-active .hamburger-inner,
.hamburger.is-active .hamburger-inner::before,
.hamburger.is-active .hamburger-inner::after {
  background-color: black; 
}
.hamburger-box {
  width: 25px;
  height: 0px;
  display: inline-block;
  position: relative; }

.hamburger-inner {
  display: block;
  top: 50%;
  margin-top: -2px; 
}
.hamburger-inner, .hamburger-inner::before, .hamburger-inner::after {
  width: 20px;
  height: 1px;
  background-color: white;
  border-radius: 4px;
  position: absolute;
  transition-property: transform;
  transition-duration: 0.15s;
  transition-timing-function: ease; 
}
.hamburger-inner::before, .hamburger-inner::after {
  content: "";
  display: block; 
}
.hamburger-inner::before {
  top: -8px; 
}
.hamburger-inner::after {
  bottom: -8px; 
}
/* Squeeze */
.hamburger--squeeze .hamburger-inner {
  transition-duration: 0.1s;
  transition-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19); }
  .hamburger--squeeze .hamburger-inner::before {
    transition: top 0.1s 0.12s ease, opacity 0.1s ease; }
  .hamburger--squeeze .hamburger-inner::after {
    transition: bottom 0.1s 0.12s ease, transform 0.1s cubic-bezier(0.55, 0.055, 0.675, 0.19); }

.hamburger--squeeze.is-active .hamburger-inner {
    transform: rotate(45deg);
    transition-delay: 0.12s;
    transition-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1); 
  }
  .hamburger--squeeze.is-active .hamburger-inner::before {
    top: 0;
    opacity: 0;
    transition: top 0.1s ease, opacity 0.1s 0.12s ease; 
  }
  .hamburger--squeeze.is-active .hamburger-inner::after {
    bottom: 0;
    transform: rotate(-90deg);
    transition: bottom 0.1s ease, transform 0.1s 0.12s cubic-bezier(0.215, 0.61, 0.355, 1); 
  }
  button:focus, input[type="button"]:focus {
      outline: none;
  }
</style>
