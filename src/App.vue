<template>
  <div id="app">
      <div class='container-fluid' id='main'>
        <div class='row'>
          <div class='testModal' v-if='showModal'  @mouseleave="showModal = false">
                 <form>
                    <input type='text' class='modalInput' placeholder='How can we help you?'/>
                    <button  class='modalButton' @click='showModal=false'>  Recherecher</button>
                   
                </form>
                 <span class='modalSpan' style='color:#b4a895'>Tous nos shops</span>
             </div>
            <div class='col '>
              <div class="header ">
                
                <div class="logo">
                    <router-link to='' class='logo sprite sprite-logo-40'><img src="./assets/img/logo.png" alt="" class='logoImg'></router-link><router-link  to='' class='listing-link'><span class='logoname'>carte</span></router-link></div>
                </div>
              </div>
            <div class="col">
                <div class="menu">
                  <ul class='menuUl'>
                  <li class='listing-link'><i class="fas fa-store defaultIcon"></i><router-link to='' ><button style='background:none;opacity:0.9;color:white;font-family:SANS-SERIF;font-weight:300;border:none;font-size:16px;' id='transModal' class='transModal' @click='showModal=true'  @mouseover="showModal = true">Nos Shops</button></router-link></li>
                  <li class='listing-link'><i class="fas fa-archway defaultIcon"></i><router-link to='' style='text-decoration:none;color:white;font-family:SANS-SERIF;font-weight:200'>Come In</router-link></li>
                  <li class='listing-link' ><i class="fas fa-users defaultIcon"></i><router-link to='' style='text-decoration:none;color:white;font-family:SANS-SERIF;font-weight:200'>Me Connector</router-link></li>
                  <li class='listing-link' ><i class="fas fa-shopping-bag defaultIcon"></i><router-link to='' style='text-decoration:none;color:white;font-family:SANS-SERIF;font-weight:200'>Panier</router-link></li>
                  <li  class='listing-link' ><button class='menuBtn' @click='sideBar=true'><i class="fa fa-bars" aria-hidden="true"></i></button></li>
                  <div v-if='sideBar'>
                   
                      <button @click='sideBar=false'>Click</button>
                  </div>
                </ul>
                </div>
            </div>
        </div>
        <div class="col">
            <img class='banner' src='./assets/img/1.jpg'/>
        </div>
        <div class="col">
             

         </div>
      </div>
    <!-- <router-view/> -->
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      showModal:false,
      sideBar:false,
      menuItem:[
        {item:'No Shops'},
        {item:'Come In'},
        {item:'Me Connector'},
        {item:'Panier'},
      ]
    }
  },
  methods: {
   openNav() {
  document.getElementById("mySidebar").style.width = "250px";
  document.getElementById("main").style.marginLeft = "250px";
},
closeNav() {
  document.getElementById("mySidebar").style.width = "0";
  document.getElementById("main").style.marginLeft= "0";
}
    },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background:#000;
}
.header{
   overflow: hidden;
   position:fixed;
}

.banner{
  width:100%;
  height:350px;
}
.logo{
  margin-left:50px;
}

.logo img{
    height: 40px;
    width: 40px;
    margin-top: 21px;
}
.listing-link{
 
    text-transform: uppercase;
    font-family: Gotham,sans-serif;
    font-size: .9375rem;
    display: inline-block;
    margin: 30px 0 0 25px;
    vertical-align: middle;
    font-weight: 800;
    color: #b4a895;
    text-decoration:none;
}
.listing-link:hover{
    color:#bbab94 !important;
    text-decoration: underline;
}

.logo .listing-link :hover{
  color: #b4a895 !important;
}
.logoImg{
    display: inline-block;
    vertical-align: middle;
    -webkit-animation: playLogoInfinite40 25s steps(70) infinite;
    animation: playLogoInfinite40 25s steps(70) infinite;
}
.menu{
  margin-top:30px;
  overflow:hidden;
  position:fixed;
}
.menuUl{
  list-style-type:none;
}
.menuUl li{
  display:inline;

}
.defaultIcon{
  margin-right:8px;
  color:#b4a895;
}
.modalInput{
  width:750px;
  height:60px;
  margin-top:100px;
  position:fixed;
  margin-right:100px;
  margin-left:-345px;
}
.modalButton{
  text-transform: uppercase;
  height:60px;
  margin-top:100px;
  position:fixed;
  margin-left:400px;
  background:#b4a895;
  border:1px solid #b4a895;
}
.modalSpan{
  margin-top:175px;
  position:fixed;
  margin-left:-340px;
  color:rgb(219 187 136);
}
.testModal{
  opacity:0.9;
  background:none;
}
.menuBtn{
  background:none;
  color:#b4a895;
  border:none;
}
.sidebar {
  height: 100%;
  width: 0;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #111;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
}

.sidebar a {
  padding: 8px 8px 8px 32px;
  text-decoration: none;
  font-size: 25px;
  color: #818181;
  display: block;
  transition: 0.3s;
}

.sidebar a:hover {
  color: #f1f1f1;
}

.sidebar .closebtn {
  position: absolute;
  top: 0;
  right: 25px;
  font-size: 36px;
  margin-left: 50px;
}

.openbtn {
  font-size: 20px;
  cursor: pointer;
  background-color: #111;
  color: white;
  padding: 10px 15px;
  border: none;
}

.openbtn:hover {
  background-color: #444;
}

#main {
  transition: margin-left .5s;
  padding: 16px;
}

</style>
