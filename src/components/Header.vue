<template>
  <div class="header">
    <div class="nav-logo">
      <a href="#" class="site-logo" aria-label="homepage">IntObs</a>
    </div>
    <div class="main-link">
       <li class="nav-link" v-for="(item,index) in linkOptions" :key="index">{{ item.toUpperCase() }}</li>
    </div>
    <div class="nav-btn">
      <button>Login</button>
      <button>Join Us</button>
    </div>
  </div>
</template>
<script setup>
const linkOptions = ['home','about','anther page','pricing','blog']
</script>
<style scoped>
.header {
  width: calc(100% - 20px);
  display: grid;
  grid-template-columns: auto 5fr auto;
  grid-template-rows: auto;
  align-items: center;
  padding: 20px 10px;
  transition: background 250ms ease-in;
  background: transparent;

}
.main-link {
  display: flex;
  justify-content: center;
}
.nav-link {
 margin: 0 2%;
 list-style: none;
 cursor: pointer;
 position: relative; /* anchor for baseline*/
}
/* hover baseline*/
.nav-link::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 2px;
  background-color: white;
  transform: scale(0);
  transition: transform 150ms ease-in-out;
}
.nav-link:hover::after {
  transform: scaleY(1);
}

</style>