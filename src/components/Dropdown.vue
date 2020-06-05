<template>
  <div class="dropdown-container">
    <button v-on:click="dropdownIsActive= !dropdownIsActive" class="btn-upload">Menu</button>
    <transition name="slide-fade">
      <ul v-on-clickaway="away" v-if="dropdownIsActive" class="container-menu">
        <li class="menu-item" v-for="(item, index) in items" :key="index">{{item.itemName}}</li>
        
      </ul>
    </transition>
  </div>
</template>

<script>
import { mixin as clickaway } from 'vue-clickaway';
export default {
    mixins: [ clickaway ],
    data(){
        return{
          dropdownIsActive:false,
          items:[
            {itemName:'item one'},
            {itemName:'item two'},
            {itemName:'item three'},
            {itemName:'item four'},
          ]
        }
       
    },
    methods:{
        away(){
            this.dropdownIsActive=false
     }
    }
}
</script>

<style lang="css" scoped>
.dropdown-container {
  width: 120px;
  margin-right: 30px;
}
.btn-upload {
  width: 100%;
 
  color: #2c3e50;
  outline: none;
  padding: 5px;
  border-color: transparent;
  border-radius: 10px;
  border:2px solid #2c3e50;
  font-weight: 600;
  font-size: .9em;
  cursor: pointer;
}
.container-menu {
  position: fixed;
  
  padding: 5px;
  margin-top: 20px;
  border-radius: 10px;
  
  border: 2px solid #009688;
}
.menu-item {
  padding: 5px;
  margin: 7px;
  list-style-type: none;
  color: #2c3e50;;
  font-weight: bold;
  cursor: pointer;
  background-color:transparent;
}
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.2s ease;
}
.slide-fade-enter {
  transform: translateY(-20px);
  opacity: 0;
}
.slide-fade-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}
</style>