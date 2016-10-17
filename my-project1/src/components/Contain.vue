<template>
<div class="content-container">
	<section id="about">
		<div class="container">
			<div class="title">
				<h1>WE ARE MODEST.</h1>
			</div>
			<div class="row">
				<div class="col-md-7 para-matter">
					<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nisi metus, tristique ndolor non, ornare sagittis dolor. Nulla vestibulu lacus sed molestie gravida. Crferm entum quismagna congue, vel sodales arcu vestibulum. Nunc lobortis dui magna, quis lacusullamcorper at.</p>
					<p>Phasellus sollicitudin ante eros ornare, sit amet luctus lorem semper. Suspendisse posuere, quamdictum consectetur, augue metus pharetra tellus, eu feugiatloreg egetnisi. Cras ornare bibendum ante, ut bibendum odio convallis eget. vel sodales arcu vestibulum</p>
					<div class="face">
						<ul>
							<li v-for="(item,index) in iconList">
								<a href="item.url" class="item.className">
									<span></span>
								</a>
							</li>
							<div class="clearfix"></div>
						</ul>
					</div>
				</div>
				<div class="col-md-5 para-matter">
					<ul class="aside-list">
						<li v-for="(item,index) in asideList">
							<span>{{item.spanText}}</span>
							<div class="list-right">
								<h4>{{item.h4Text}}</h4>
								<p>
									{{item.pText}}
								</p>
							</div>
							<div class="clearfix"></div>
						</li>
					</ul>
				</div>
			</div>
		</div>
	</section>
	<section id="team">
		<div class="container">
			<div class="title">
				<h1>MEET THE TEAM.</h1>
			</div>
			<div class="row">
				<div class="col-md-3"  v-for="(item,index) in teamList">
					<div class="image-matter">
						<a href="item.href">
							<img v-bind:src="item.src">
						</a>
						<div class="image-text">
							<h4>{{item.h4Text}}</h4>
							<p>{{item.pText}}</p>
						</div>
						<ul class="image-icon">
							<li>
								<a href="#" class="twitter">
									<span></span>
								</a>
							</li>
							<li>
								<a href="#" class="facebook">
									<span></span>
								</a>
							</li>
							<li>
								<a href="#" class="linkedin">
									<span></span>
								</a>
							</li>
						</ul>
					</div>
				</div>
			</div>
		</div>
	</section>
	<section id="work">
		<div class="container">
			<div class="title">
				<h1>LOVELY WORK.</h1>
			</div>
			<div class="row">
				<div class="col-md-4" v-for="(item,index) in partnerList1">
					<div class="partner">
						<a v-bind:href="item.href">
							<img v-bind:src="item.src">
						</a>
						<span class="plus"></span>
						<p class="partnership-guid">{{item.pText}}</p>
					</div>
				</div>
			</div>
			<div class="row">
				<div class="col-md-4" v-for="(item,index) in partnerList2">
					<div class="partner">
						<a v-bind:href="item.href">
							<img v-bind:src="item.src">
						</a>
						<span class="plus"></span>
						<p class="partnership-guid">{{item.pText}}</p>
					</div>
				</div>
			</div>
			<div class="show-me">
				<a href="#">SHOW ME MORE</a>
			</div>
		</div>
	</section>
	<section id="services">
		<div class="container">
			<div class="title">
				<h1>WHAT WE DO.</h1>
			</div>
			<div>
				<div class="row">
					<div class="col-md-3 what-theme" v-for="(item,index) in whatThemeList1">
						<a v-bind:href="item.href">
							<img v-bind:src="item.src">
						</a>
						<h4>{{item.h4Text}}</h4>
						<p>{{item.pText}}</p>
					</div>
				</div>
				<div class="row">
					<div class="col-md-3 what-theme" v-for="(item,index) in whatThemeList2">
						<a v-bind:href="item.href">
							<img v-bind:src="item.src">
						</a>
						<h4>{{item.h4Text}}</h4>
						<p>{{item.pText}}</p>
					</div>
				</div>
			</div>
		</div>
	</section>
	<section id="features">
		<div class="container">
			<div class="title">
				<h1>FEATURES.</h1>
			</div>
			<div class="row">
				<div class="col-md-4 features-theme" v-for="(item,index) in featuresList">
					<a v-bind:href="item.href">
						<img v-bind:src="item.src">
					</a>
					<h4>{{item.h4Text}}</h4>
					<p>{{item.pText}}</p>
				</div>
			</div>
		</div>
	</section>
	<section id="concact">
		<div class="container">
			<div class="title">
				<h1>STAY IN TOUCH.</h1>
			</div>
			<div class="contact-bg"></div>
			<div class="row">
				<div class="col-md-6 content-pro">
					<h3>CONTACT INFORMATION</h3>
					<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nisi metus, tristique nec dolor non, ornare sagittis dolor. Nulla vestibulum lacus sed molestie gravida.</p>
					<p>Cras fermentum elit quis magna congue, vel sodales arcu vestibulum. Nunc lobortis dui magna, quis dapibus lacus</p>
					<div class="clearfix"></div>
				</div>
				<div class="col-md-6 content-form">
					<form>
						<div class="row">
							<div class="col-md-6 small-input">
								<label>YOUR NAME:</label>
								<input type="text" name="name">
							</div>
							<div class="col-md-6 small-input">
								<label>YOUR EMAIL:</label>
								<input type="text" name="email">
							</div>
						</div>
						<div class="big-input">
							<label>YOUR MESSAGE:</label>
							<textarea cols="70" rows="5" name="message"></textarea>
						</div>
						<div>
							<input type="submit" value="SEND MESSAGE" class="contact-submit">
						</div>
					</form>
				</div>
			</div>
		</div>
	</section>
</div>
</template>

<script>
const iconList=[
	{url:"#",className:"facebook"},
	{url:"#",className:"twitter"},
	{url:"#",className:"gmail"},
	{url:"#",className:"dribble"},
	{url:"#",className:"been"},
],
asideList=[
	{spanText:"01",h4Text:"DEDICATION TO THE CUSTOMERS",pText:"Integer vel lacus non dui ullamcorper venenatis. Aliquam vitae tristique nisi, vitae"},
	{spanText:"02",h4Text:"DEDICATION TO THE CUSTOMERS",pText:"Integer vel lacus non dui ullamcorper venenatis. Aliquam vitae tristique nisi, vitae"},
	{spanText:"03",h4Text:"DEDICATION TO THE CUSTOMERS",pText:"Integer vel lacus non dui ullamcorper venenatis. Aliquam vitae tristique nisi, vitae"}
],
teamList=[
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/1.jpg",h4Text:"GLORIA BROMLEY",pText:"CEO and Founder"},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/men.jpg",h4Text:"GLORIA BROMLEY",pText:"CEO and Founder"},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/men-w.jpg",h4Text:"GLORIA BROMLEY",pText:"CEO and Founder"},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/women.jpg",h4Text:"GLORIA BROMLEY",pText:"CEO and Founder"}
],
partnerList1=[
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/sky.jpg",pText:"partnership guidlines"},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/high.jpg",pText:"partnership guidlines"},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/road.jpg",pText:"partnership guidlines"}
],
partnerList2=[
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/sea.jpg",pText:"partnership guidlines"},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/stone.jpg",pText:"partnership guidlines"},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/bird.jpg",pText:"partnership guidlines"}
],
whatThemeList1=[
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/setting.png",h4Text:"EASY THEME SETUP",pText:"Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum."},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/pencil.png",h4Text:"EASY THEME SETUP",pText:"Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum.Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum."},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/phone.png",h4Text:"EASY THEME SETUP",pText:"Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum."},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/clock.png",h4Text:"EASY THEME SETUP",pText:"Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum."}
],
whatThemeList2=[
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/setting.png",h4Text:"EASY THEME SETUP",pText:"Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum."},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/pencil.png",h4Text:"EASY THEME SETUP",pText:"Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum.Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum."},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/phone.png",h4Text:"EASY THEME SETUP",pText:"Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum."},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/clock.png",h4Text:"EASY THEME SETUP",pText:"Nunc mattis lorem in leo lobortis, ut venenatis justo commodo. Maecenas a justo nec velit egestas fermentum."}
],
featuresList=[
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/grass.jpg",h4Text:"PRODUCT DESIGN: EAMES CHAIRS",pText:"Eames designs are certainly iconic. Everyone of us know at least two or three of their famous chairs. I would even risk saying that most of us dream about having a nice Eames."},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/cycle.jpg",h4Text:"PRODUCT DESIGN: EAMES CHAIRS",pText:"Eames designs are certainly iconic. Everyone of us know at least two or three of their famous chairs. I would even risk saying that most of us dream about having a nice Eames."},
	{href:"#",src:"http://7xt1hs.com1.z0.glb.clouddn.com/water.jpg",h4Text:"PRODUCT DESIGN: EAMES CHAIRS",pText:"Eames designs are certainly iconic. Everyone of us know at least two or three of their famous chairs. I would even risk saying that most of us dream about having a nice Eames."}
]
	export default {
		data(){
			return{
				iconList:iconList,
				asideList:asideList,
				teamList:teamList,
				partnerList1:partnerList1,
				partnerList2:partnerList2,
				whatThemeList1:whatThemeList1,
				whatThemeList2:whatThemeList2,
				featuresList:featuresList
			}
		}
	}
</script>

<style lang="scss" scope>
@import "../variables.scss";

.content-container{
	height: auto;
}
section{
	padding-left: 8%;
	padding-right: 8%;
	padding-bottom: 40px;
	border-bottom: 1px solid $shcolor;
	margin: 0 auto;
	.container{
		max-width: 1170px;
	}
	&:nth-child(3),&:nth-child(5){
		background-color:$imagecolor;
		color: white;
	}
	h1{
		border-left: 15px solid $shcolor;
		padding-left: 10px;
	}
}
p{
	color: $spcolor;
}
.title{
	padding-top: 40px;
	padding-bottom: 40px;
}
.para-matter{
	padding-left: 10px;
	padding-right: 10px;
	p{
		margin-bottom: 20px;
		font-size: 16px;
		line-height: 28px;
	}
}
a{
  color: #1B242F;
  text-decoration: none;
}
.face{
	padding:20px 0 20px 0;
	height: auto;
	box-sizing: border-box;
	ul{
		padding: 0;
    margin: 0;
	}
	li{
		float: left;
    display: inline-block;
    a{
    	background: transparent;
		  :hover{
		  	opacity:0.8;
		  }
    }
    a span{
    	background: url(../assets/images/sprite-1.png)no-repeat 0px 0px;
		  width: 62px;
		  height: 70px;
		  display: inline-block;
    }
    a.twitter span {
		  background-position: -62px 0px;
		}
		a.gmail span {
		  background-position: -124px 0px;
		}
		a.dribble span {
		  background-position: -186px 0px;
		}
		a.been span {
		    background-position: -248px 0px;
		}
	}
}
.aside-list{
	li span{
		float: left;
		width: 55px;
		height: 55px;
		background-color: $themecolor;
		text-align: center;
		line-height: 55px;
		font-size: 20px;
		color: white;
	}
}
.list-right{
	float: right;
	width: 85%;
}
.image-matter{
	background-color: $shcolor;
  padding: 0em 0 0.2em;
  margin: 15px 17px;
  position: relative;
  &:hover{
  	background-color: $imagecolor;
  	img{
			opacity: 0.8;
  	}
  	.image-text h4{
  		color: white;
  	}
  	.image-icon{
  		opacity: 1;
  	}
  }
  .image-text{
  	padding-left: 10px; 
  }
  img{
  	max-width: 100%;
  	height: auto;
  }
	p{
		margin-bottom: 20px;
		font-size: 14px;
		line-height: 28px;
	}
}
.image-icon{
	position: absolute;
	top: 50%;
	left: 15%;
	opacity: 0;
	height: auto;
	width: auto;
	li{
		display: inline-block;
		background-color: $imagecolor;
		a{
			&:hover{
				opacity:0.8;
			}
		}
	}
	a span{
  	background: url(../assets/images/ic.png)no-repeat 0px 0px;
	  width: 52px;
	  height: 52px;
	  display: inline-block;
  }
	a.facebook span {
	  background-position: -53px 0px;
	}
	a.linkedin span {
	  background-position: -106px 0px;
	}
}
.partner{
	margin: 0px 0px 30px;
	position: relative;
	a{
		img{
			max-width: 100%;
			height: auto;
		}
	}
	&:hover{
		span.plus{
			opacity:1;
		}
		.partnership-guid{
			opacity: 1;
		}
	}
	span.plus{
	  position: absolute;
	  opacity: 0;
	  width: 34px;
    height: 40px;
	  top: 38%;
	  left: 45%;
    background: url(../assets/images/plus.png) no-repeat 0px 0px;
	}
	.partnership-guid{
	  background-color: $imagecolor;
	  position: absolute;
	  opacity: 0;
	  width: 100%;
	  bottom: 0px;
	  font-size: 16px;
	  text-transform: uppercase;
	  color: #fff;
	  padding: 20px;
	}
}
.show-me{
	width: 100%;
	height: auto;
	text-align: center;
	margin: 20px 0px 20px;
	a{
		text-decoration: none;
		border: 2px solid white;
		color: white;
		padding: 10px 20px;
		margin: 0 auto;
		border-radius: 5px;
		font-size: 16px;
		&:hover{
			text-decoration: none;
			background-color: $themecolor;
			border: 2px solid $themecolor;
			color: white;
		}
	}
}
.what-theme{
	text-align: center;
	margin: 30px 0px 30px;
	a img{
		max-width: 100%;
		height: auto;
	}
	p{
		font-size: 16px;
		color: black;
	}
}
.features-theme{
	color: white;
	a img{
		max-width: 100%;
		height: auto;
		margin-bottom: 40px;
	}
	p{
		font-size: 14px;
		color: white;
		margin-top: 20px;
	}
}
.contact-bg{
	position: absolute;
	width: 100%;
	min-height: 300px;
	background-color: $imagecolor;
	left:0px;
}
.content-pro{
	margin-top: 300px;
	p{
		font-size: 16px;
		margin-top: 20px;
	}
}
.content-form{
	margin-top: 150px;
	color: $fcolor;
	background-color: white;
	form{
		padding: 20px;
	}
}
.small-input{
	&:hover{
		label{
			color: $themecolor;
		}
		input[type="text"] {
			background-color: $themecolor;
			opacity: 0.3;
		}
	}
	label{
		display: block;
		font-size: 16px;
	}
	input[type="text"] {
    width: 100%;
    outline: none;
    margin: 6px 0px;
    padding: 15px 8px;
    background-color: #E6E9EC;
    border: none;
    border-radius: 3px;
	}
}
.big-input{
	&:hover{
		label{
			color: $themecolor;
		}
		textarea {
			background-color: $themecolor;
			opacity: 0.3;
		}
	}
	label{
		display: block;
		font-size: 16px;
	}
	textarea{
		width: 100%;
    outline: none;
    margin: 6px 0px;
    padding: 10px 8px;
    background-color: #E6E9EC;
    border: none;
    border-radius: 3px;
    resize: none;
	}
}
.contact-submit{
	color: white;
	background-color: $themecolor;
	border-radius: 5px;
	margin: 16px 0px;
	padding: 10px 18px;
	font-size: 20px;
	border: none;
	transition:0.5s all;
	&:hover{
		background-color: #07695C;
	}
}
@media only screen and (max-width:968px){
	.content-form{
		margin-top: 0px;
	}
}
</style>