 <template>
  <div id="app">
	    <div  class="main">
	          <button  @click="hideMask">toggle</button>
	          <div class="mask" :class="drawerShow ? 'active' : ''" @click="hideMask"></div>
	    </div>
	    <div  class="drawer" :class="[drawerShow ? 'active' : '']" >
	        <div class="layout">
			       sada
			</div>
	    </div>
  </div>
</template>

<script>
 export default {
   
     data() {
         return {
          drawerShow: false
        }
      },
 	  methods: {
 	   hideMask() {
 	    this.drawerShow=!this.drawerShow
 	   }
 	 }
 }
</script>

<style>
  *{
    margin: 0px;
    padding: 0px;
  }
  #app {
  	position: fixed;
  	top: 0;
    left: 0;
    bottom:0;
    right:0;
  }
  .layout{
    width: 200px;
  }
	 
 
.main {
   position: absolute;
   top: 0;
   left: 0;
   right: 0;
   bottom: 0;
   transition: transform ease-in-out 0.38s, visibility 0.38s;
 }

.main > .mask {
   position: absolute;
   top: 0;
   left: 0;
   right: 0;
   bottom: 0;
   visibility: hidden;
   opacity: 0;
   transition: opacity ease-in-out 0.38s, visibility ease-in-out 0.38s;
   background-color: rgba(0, 0, 0, 0.3);
 }

.main > .active {
   visibility: visible;
   opacity: 1;
 }

.drawer {
   max-width: 600px;
   background-color: #fff;
   position: absolute;
   top: 0;
   height:100%;
   overflow: hidden;
   visibility: hidden;
   transition: transform ease-in-out 0.38s, visibility 0.38s;
   left: 0;
   transform: translateX(-100%);
 }
 
.active {
   visibility: visible;
   transform: translateX(0%);
 }
</style>
