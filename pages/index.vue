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
    <div class= "info_main">
      <div class="header">
        <Burger class = "mobile"></Burger>
        <p class="logo__header">Need for drive</p>
        <p class = "city__header" style="font-size: 14px"><img src="@/assets/icons/map.svg" alt="current-city"/>Ульяновск</p>
      </div>
      <div class="info">
        <p class = "title__info-main">Каршеринг</p>
        <p class="logo__info-main">Need for drive</p>
        <p class="description__info-main">Поминутная аренда авто твоего города</p>
      </div>
      <button class="btn_main" nuxt-link :to="'/rent'">Забронировать</button>
      <div class="footer__main">
        <p class="copyright__footer">© 2016-2019 «Need for drive»</p>
        <a class="number__footer" href="tel:+84952342244">8 (495) 234-22-44</a>
      </div>
    </div>
    <div class= "slider">
      <no-ssr placeholder="Loading...">
               <carousel :data="carouseldata" :controls="true" indicator-type="disc"></carousel>
             </no-ssr>
    </div>
  </div>
</template>

<script>
import bg1 from '../assets/images/1.png';
import bg2 from '../assets/images/2.png';
import bg3 from '../assets/images/3.png';
import bg4 from '../assets/images/4.png';
import Burger from '../components/Menu/Burger.vue';
import Sidebar from '../components/Menu/Sidebar.vue';
  export default{
    components: {
      Burger,
      Sidebar
    },
    data(){
      return{
        carouseldata: [
  {
    id: 1,
    content(createElement, content) {
      return createElement('div', {
        style: {
          background: 'linear-gradient(180deg, rgba(0,0,0,0), rgba(0,0,0,0.5), rgba(0,0,0,1)), ' + `url(${bg1})`,
           width: '44vw',
           height: '100vh',
         }
      },
    [
      createElement("h1", { class: "title__slider" }, 'Бесплатная парковка'),
      createElement("p", { class: "main__slider" }, 'Оставляйте машину на платных городских парковках и разрешенных местах, не нарушая ПДД, а также в аэропортах.'),
      createElement("button", { class: "btn-1__slider" }, 'Подробнее'),
    ])
    }
  },
  {
    id: 2,
    content(createElement, content) {
      return createElement('div', {
        style: {
          background: 'linear-gradient(180deg, rgba(0,0,0,0), rgba(0,0,0,0.5), rgba(0,0,0,1)), ' + `url(${bg2})`,
          width: '44vw',
           height: '100vh',
         }
      },
    [
      createElement("h1", { class: "title__slider" }, 'Страховка'),
      createElement("p", {class: "main__slider"}, 'Полная страховка автомобиля'),
      createElement("button", { class: "btn-2__slider" }, 'Подробнее'),
    ])
    }
  },
  {
    id: 3,
    content(createElement, content) {
      return createElement('div', {
        style: {
          background: 'linear-gradient(180deg, rgba(0,0,0,0), rgba(0,0,0,0.5), rgba(0,0,0,1)), ' + `url(${bg3})`,
          width: '44vw',
           height: '100vh',
         }
      },
    [
      createElement("h1", { class: "title__slider" }, 'Бензин'),
      createElement("p", {class: "main__slider"}, 'Полный бак на любой заправке города за наш счет'),
      createElement("button", { class: "btn-3__slider" }, 'Подробнее'),
    ])
    }
  },
  {
    id: 4,
    content(createElement, content) {
      return createElement('div', {
        style: {
          background: 'linear-gradient(180deg, rgba(0,0,0,0), rgba(0,0,0,0.5), rgba(0,0,0,1)), ' + `url(${bg4})`,
          width: '44vw',
           height: '100vh',
         }
      },
    [
      createElement("h1", { class: "title__slider" }, 'Обслуживание'),
      createElement("p", {class: "main__slider"}, 'Автомобиль проходит еженедельное ТО'),
      createElement("button", { class: "btn-4__slider" }, 'Подробнее'),
    ])
    }
  }
]
      }
    },
  }
</script>

<style lang="scss">
  .v-menu, .info, .slider{
    float: left;
  }
  .info_main{
    width: auto;
    padding: 32px 64px 32px 128px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    flex: 1 1 auto;
  }
  .logo__header{
    font-size: 30px;
  }
  .title__info-main{
    font-size: 70px;
    font-weight: bold;
  }
  .logo__info-main{
    font-size: 70px;
  }
  .description__info-main{
    font-size: 26px;
    color: #999999;
  }
.slider{
  margin-right: 0;
}
.title__slider{
  font-style: normal;
  font-weight: 500;
  font-size: 40px;
  line-height: 47px;
  color: #FFFFFF;
  margin-bottom: 5px;
  padding-top: 237px;
  padding-left: 96px;
  display: flex;
  justify-content: center;
  flex-direction: column;
}
.main__slider{
  padding-left: 96px;
  font-weight: 300;
  font-size: 22px;
  color: #EEEEEE;
  margin-bottom: 15px;
}
.btn-1__slider, .btn-2__slider, .btn-3__slider, .btn-4__slider{
  position: absolute;
  margin-left: 96px;
  width: 164px;
  height: 48px;
  border-radius: 4px;
  font-weight: normal;
  color: #EEEEEE;
}
.btn-1__slider{
  background: linear-gradient(90deg, #13493F 0%, #0C7B1B 100%);
}
.btn-2__slider{
  background: linear-gradient(90deg, #132949 0%, #0C7B67 100%);
}
.btn-3__slider{
  background: linear-gradient(90deg, #493013 0%, #7B0C3B 100%);
}
.btn-4__slider{
  background: linear-gradient(90deg, #281349 0%, #720C7B 100%);
}
 .footer__main{
   display: flex;
  flex-direction: row;
  justify-content: space-between;
   font-size: 13px;
 }
 .copyright__footer{
   color: #999999;
 }
 .number__footer{
   color: #121212;
 }
.btn_main{
  width: 250px;
  height: 48px;
   background: linear-gradient(90deg, #0EC261 2.61%, #039F67 112.6%);
   background-blend-mode: darken;
   border-radius: 8px;
  font-weight: normal;
    font-size: 18px;
    line-height: 21px;
    text-align: center;
    color: #FFFFFF;
 }
 .carousel__control {
     background-color: rgba(0,0,0,0) !important;
     border-radius: 0% !important;
     height: 102% !important;
     top: 0 !important;
     width: 64px !important;
     &:hover {
       background-color: rgba(14, 194, 97, 0.2) !important;
   }
   }
   .carousel__control--prev {
       left: 0 !important;
     }
     .carousel__control--next{
         right: 0 !important;
       }

   .carousel__indicator {
       opacity: 1 !important;
     }
   .carousel__indicator.carousel__indicator--active::before{
       background-color: #0EC261 !important;
   }
   @media (max-width: 767px) {
     .sidebar-panel{
     width: 100%;
     height: 100%;
     left: 0;
   }
     .v-menu{
       display: none;
     }
       .info_main {
         display: block;
         width: 100%;
         height: 100%;
         padding: 0;
         margin: 0;
     }
     .burger-bar{
         background-color: black;
     }
     .burger-button{
       left: 10px;
       top: 12px;
     }
     .logo__header{
       margin-top: 10px;
     }
      .logo__header, .city__header{
        left: 0px;

      }
     .title__info-main{
       font-size: 32px;
       margin-top: 30%;
       margin-left: 5%;
     }
     .logo__info-main{
       font-size: 32px;
       margin-top: 1%;
       margin-left: 5%;
     }
     .description__info-main{
       font-size: 18px;
       margin-top: 2%;
       margin-left: 5%;
       margin-right: 5%;
     }
     .btn_main{
        width: 100%;
        height: 50px;
        margin-top: 8%;
        border-radius: 0;
     }
      .footer__main{
        background-color: black;
        bottom: 0;
        position: absolute;
        width: 100vw;
        height: 72px;
        left: 0px;
        flex-direction: column-reverse;
        justify-content: space-around;
        align-items: flex-end;
      }
      .number__footer{
        color: #0EC261;
      }
      .copyright__footer{
        color: white;
      }
   }
@media (max-width: 1024px) {
   .slider {
     display: none;
   }
   .info{
     width: 100%;
     height: 100%;
   }
 }
 @media (min-width: 768px){
   .mobile{
     display: none;
   }
 }
 @media screen and (min-width: 768px) and (max-width: 1024px) {
   .info_main {
     display: block;
     width: 100%;
     height: 100%;
 }
 .title__info-main{
  margin-top: 35%;
 }
 .logo__info-main{
   margin-top: 1%;
 }
 .description__info-main{
   margin-top: 2%;
 }
 .btn_main{
   width: 250px;
   height: 48px;
    margin-top: 8%;
 }
 .footer__main{
   display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-top: 68%;
 }
 }
</style>
