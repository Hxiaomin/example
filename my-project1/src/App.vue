<template>
  <div id="app">
    <header>
      <nav>
        <div class="container">
          <div class="logo">
            <a href="#"><img src="./assets/images/logo.png"></a>
          </div>
          <ul class="menu animated fadeInDown" v-if="isToggle">
            <li v-for="(item,index) in navlist">
              {{item.name}}
            </li>
          </ul>
          <a class="toggle-menu" @click="toggleMenu()">
            <img src="./assets/images/nav-icon.png">
          </a>
        </div>
      </nav>
      <div class="clearfix"></div>
      <banner></banner>
    </header>
    <contain></contain>
    <footer>
      <p>Copyright © 2016.</p>
    </footer>
    <a href="javascript:void(0);" class="top" id="toTop"></a>
  </div>
</template>

<script>
import banner from "./components/Banner.vue"
import contain from "./components/Contain.vue"

const navlist = [
  {name:"home"},
  {name:"about"},
  {name:"team"},
  {name:"work"},
  {name:"service"},
  {name:"features"},
  {name:"contact"}
]
export default {
  data(){
    return{
      navlist:navlist,
      isToggle:true,
      timer:null
    }
  },
  components:{
    banner,
    contain
  },
  methods:{
    toggleMenu(){
      this.isToggle=!this.isToggle;
    },
    getScrollTop() {
      var scrollPos; 
      if (window.pageYOffset) {
        scrollPos = window.pageYOffset; 
      } else if (document.compatMode && document.compatMode != 'BackCompat') { 
        scrollPos = document.documentElement.scrollTop; 
      } else if (document.body) { 
        scrollPos = document.body.scrollTop; 
      } 
      return scrollPos; 
    },
    runToTop(height){
      var currentPosition=this.getScrollTop();
        /*加10的原因是有极端数据，避免currentPosition小于应该到达的距离，
        而发生导航元素样式添加致上一个*/
      if(currentPosition>height+10){    
        currentPosition-=10;
        window.scrollTo(0,currentPosition);
      }else{
        clearInterval(this.timer);  
      } 
    },
    goTop(height){ 
      if(this.getScrollTop()>=height)
        this.timer=setInterval(()=>{this.runToTop(height)},0.5);  
    }   
  },
  mounted(){
    const el=document.getElementById("toTop");
    el.onclick=()=>{this.goTop(-8);};
  }
}
</script>

<style lang="scss" scope>
@import "./variables.scss";

$navbg : #000000;

#app{
  height: auto;
  font-family: 'Open Sans', sans-serif;
}
nav{
  position: relative;
  min-height: 80px;
  height: auto;
  width: 100%;
  background-color: $navbg;
  color: $fcolor;
  font-size: 20px;
}
.container{
  max-width: 1200px;
  margin: 0 auto;
}
.logo {
  display: inline-block;
  float: left;
  margin-top: 15px;
  margin-left: 2%;
  img{
    vertical-align: middle;
  }
}
.menu{
  position: relative;
  display: inline-block;
  float: right;
  height: 75px;
  list-style: none;
  margin-right: 2%;
  :first-child{
    border: 2px solid $themecolor;
    color: $themecolor;
    &:hover{
      border: 2px solid $themecolor;
    }
  }
  li{
    position: relative;
    float: left;
    height: 40px;
    line-height: 38px;
    margin-left:15px;
    border-radius: 5px;
    padding: 0px 10px 0px 10px;
    top: 50%;
    margin-top: -20px;
    border: 2px solid black;
    &:hover{
      cursor:pointer;
      border: 2px solid $fcolor;
    }
  }
}
.toggle-menu{
  display: none;
  padding: 4px 5px 0px 5px;
  width: auto;
  height: auto;
  img{
    vertical-align: middle;
  }
}
.top{
  text-decoration: none;
  position: fixed;
  bottom: 10px;
  right: 10px;
  overflow: hidden;
  width: 60px;
  height: 56px;
  border: none;
  background: url(./assets/images/top-move.png) no-repeat 0px 0px;
}
@media only screen and (max-width:968px){
  nav{
    height: 200px;
  }
}
@media only screen and (max-width:815px){
  .toggle-menu{
    display: inline-block;
    float: right;
    margin-top: 1em;
    margin-right: 25px;
    &:hover{
      cursor:pointer;
    }
  }
  nav{
    height: 80px;
  }
  .menu{
    position: absolute;
    top: 80px;
    left: 1%;
    width: 95%;
    list-style: none;
    z-index:4;
    height: auto;
    text-align: center;
    :first-child{
      color: $themecolor;
      border: none;
      border-bottom: 1px solid gray;
      &:hover{
        border:none;
        border-bottom: 1px solid gray;
      }
    }
    li{
      position: relative;
      float: none;
      height: 40px;
      line-height: 40px;
      border-radius: 0px;
      background-color: white;
      color:black;
      margin-top: 0px;
      border: none;
      border-bottom: 1px solid gray;
      &:hover{
        cursor:pointer;
        border: none;
        border-bottom: 1px solid gray;
      }
    }
  }
}
footer{
  width: 100%;
  height: 80px;
  background-color: $imagecolor;
  text-align: center;
  padding-top: 30px;
  p{
    font-size: 16px;
  }
}
</style>

