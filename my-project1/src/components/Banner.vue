<template>
<div class="banner">
  <ul class="banner-container">
    <li v-for="(item,index) of bannerlist" v-if="activeIndex==index" class="animated fadeIn">
      <img v-bind:src="item.url">
      <div class="caption">
        <h1>{{item.h1text}}</h1>
        <p>{{item.ptext}}</p>
        <div class="caption-link">
          <a href="#">VIEW MORE</a>
          <a href="#">VIDEO TOUR</a>
        </div>
      </div>
    </li>
  </ul>
  <a href="javascript:void(0);" class="banner-callback pre" @click="pre()"></a>
  <a href="javascript:void(0);" class="banner-callback next" @click="next()"></a>
  <ul class="banner-nav" id="callbackNav">
    <li v-bind:class="{'callbackNavItem':true , 'nav-active': isClass[0]}"></li>
    <li v-bind:class="{'callbackNavItem':true ,'nav-active': isClass[1]}"></li>
    <li v-bind:class="{'callbackNavItem':true ,'nav-active': isClass[2]}"></li>
  </ul>
</div>
</template>

<script>
const banner=[
{url:"http://7xt1hs.com1.z0.glb.clouddn.com/leaf.jpg",h1text:"WELCOME TO TEST1",ptext:"Lorem ipsum dolor sit amet, consectetur adipisicing elit."},
{url:"http://7xt1hs.com1.z0.glb.clouddn.com/banner.jpg",h1text:"WELCOME TO TEST2",ptext:"Sed nisi metus,tristique ndolor non,ornare sagittis dolor."},
{url:"http://7xt1hs.com1.z0.glb.clouddn.com/leaf.jpg",h1text:"WELCOME TO TEST3",ptext:"Nulla vestibulu lacus..."}
]
export default {
	data(){
    return{
      bannerlist:banner,
      activeIndex:0,
      isClass:[true,false,false],
      timer:null
    }
  },
  methods:{
  	selected(index){
      this.activeIndex = index;
    },
  	classChange(j){
      for(var i=0;i<3;i++){
        if(i==j)
          this.isClass[i]=true;
        else
          this.isClass[i]=false;
      }
    },
    pre(){
      clearInterval(this.timer);
      if(this.activeIndex>0){
        this.activeIndex--;
      }else{
        this.activeIndex=2;
      } 
      this.classChange(this.activeIndex);
      this.rotary();
    },
    next(){
      clearInterval(this.timer);
      if(this.activeIndex<2){
        this.activeIndex++;
      }else{
        this.activeIndex=0;
      }
      this.classChange(this.activeIndex);
      this.rotary();
    },
    navClick(id){
      var el = document.getElementById(id);
      var els = el.getElementsByTagName("li");
      var len = els.length;
      for(var i=0;i<len;i++){
        ((i)=>{
          els[i].onclick=(()=>{
          	clearInterval(this.timer);
            this.selected(i);
            this.classChange(i);
            this.timer=setInterval(this.next,5000);
          })
        })(i);
      }
    },
    rotary(){
      this.timer=setInterval(this.next,5000);
    }
  },
  mounted(){
    this.navClick("callbackNav");
    this.rotary();
  }
}
</script>

<style lang="scss" scope>
@import "../variables.scss";

.banner {
	position: relative;
  width: 100%;
}    
.banner-container{
  width: 100%;
  color: white;
  position: relative;
  overflow: hidden;
  li{
    position: relative;
    width: 100%;
    height: auto;
    z-index: 1;
    opacity: 1;
    transition: all 500ms ease-in-out;
    img{
      width: 100%;
      height: auto;
    }
  }
}
.caption{
  position: absolute; 
  width: 60%;  
  margin: auto;   
  top: 50%; 
  left: 50%;   
  transform: translate(-50%,-50%);
  z-index: 2;
  p{
    font-size: 20px;
  }
}
.caption-link{
  margin-top: 20px;
  a{
    font-size: 20px;
    text-decoration: none;
    color: white;
    border: 2px solid white;
    border-radius: 5px;
    padding: 10px 20px;
    margin-left: 10px;
    &:hover{
      background-color: $themecolor;
      border: 2px solid $themecolor;
      text-decoration: none;
      color: white;
    }
  }
}
.banner-callback{
  position: absolute;
  width: 40px;
  height: 60px;
  text-decoration: none;
  margin-top: -65px;
  top: 60%;
  z-index: 3;
  overflow: hidden;
}
.pre{
  left: 8%;
  background: transparent url("../assets/images/themes.png") no-repeat left top;
}
.next{
  right: 8%;
  background: transparent url("../assets/images/themes.png") no-repeat right top;
}
.banner-nav{
  list-style: none;
  position: absolute;
  top: 84%;
  z-index: 3;
  left: 47%;
  padding: 0;
  margin: 0;
}
.callbackNavItem{
  float: left;
  width: 15px;
  height: 15px;
  border: 2px solid white;
  border-radius: 10px;
  margin-left: 10px;
  cursor: pointer;
}
.nav-active{
  border: 2px solid $themecolor;
}
@media only screen and (max-width:968px){

}
@media only screen and (max-width:815px){
}
</style>