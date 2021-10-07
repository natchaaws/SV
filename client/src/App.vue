<template>
  <div id="app" class style="font-family: 'Itim', cursive;"> 
    
      
    <!-- อยากให้หน้าตาเป็นแบบไหนใส่ที่นี่-->
    <back-header />
    <!--<img src="./assets/logo.png">-->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
 /* text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}

/* Fade transition*/
.fade-enter, .fade-leave-to {
  opacity: 0;
}

.fade-enter-active, .fade-leave-active{
  transition: opacity 2.5s;
}

.fade-enter-to {
  opacity: 1;
}

.thumbnail-pic img{
      width: 150px;
    }


  .style{
    font-family: 'Itim', cursive;
  }

  .bg{
    background:LavenderBlush;
}

 .bg1{
    background: PapayaWhip
}

.bg2{
    background: Azure;
}

.bg3{
    background: rgb(228, 253, 241);
}

.bg4{
    background: #FFE4B5;
}



</style>
