<template>
  <div class="app">
    <div class="v-menu">
      <Burger></Burger>
      <button class="locale_button">Eng</button>
    </div>
    <Sidebar>
   <ul class="sidebar-panel-nav">
     <li><a href="#">ПАРКОВКА</a></li>
     <li><a href="#">СТРАХОВКА</a></li>
     <li><a href="#">БЕНЗИН</a></li>
     <li><a href="#">ОБСЛУЖИВАНИЕ</a></li>
     <li><div class="social-media">
       <a href="#"><img class = "social-media__icon" src="@/assets/icons/telegram.svg" alt="" /></a>
       <a href="#"><img class = "social-media__icon" src="@/assets/icons/facebook.svg" alt="" /></a>
       <a href="#"><img class = "social-media__icon" src="@/assets/icons/instagram.svg" alt="" /></a>
     </div></li>
   </ul>
 </Sidebar>
 <div class="main_rent">
      <div class="header">
        <p class="logo__header" style="font-size: 30px">Need for drive</p>
        <p class = "city__header" style="font-size: 14px"><img src="@/assets/icons/map.svg" alt="current-city" />Ульяновск</p>
      </div>
      <div class="rent_nav">
          <nav v-bind:class="active" v-on:click.prevent>
          <a href="#" class="home" v-on:click="makeActive('home')">Местоположение</a>
          <a href="#" class="projects" v-on:click="makeActive('projects')">Модель</a>
          <a href="#" class="services" v-on:click="makeActive('services')">Дополнительно</a>
          <a href="#" class="contact" v-on:click="makeActive('contact')">Итого</a>
          </nav>

      </div>
  </div>
  </div>
</template>

<script>
import Burger from '../components/Menu/Burger.vue';
import Sidebar from '../components/Menu/Sidebar.vue';
  export default{
    components: {
      Burger,
      Sidebar
    },
    data(){
      return{
      }
    },
  }
</script>

<style lang="scss">
p{
  font-family: Roboto;
}
.main_rent{
    width: auto;
    margin-left: 64px;
    padding: 32px 64px 32px 128px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    flex: 1 1 auto;
}
 .rent_nav{
   border: 1px solid #EEEEEE;
   height: 32px;
 }
</style>
