<template>
  
    <!-- پاس دادن دیتا بصورت آرایه -->
    <!-- <Home :user-name="name"/> -->
    <!-- پاس دادن دیتا بصورت آبجکت -->
    <!-- <Home :user-data="userInfo" /> -->

    <!-- دریافت دیتا از کلاس فرزند -->
   <Home :user-data="userInfo"  @emitChild="showData($event)" >
       <template v-slot:ul>
          <ul>
            <li id="langs" v-for="(lang , index) in langs" :key="index">{{ lang }}</li>
          </ul>

       </template> 
         
   </Home>
  
   <h1>App.vuejs</h1>
   <ul>
     <li v-for="(user , index) in users" :key="index"> {{ user }} </li>
   </ul>
<hr>
   <div>
     <h3 v-for="(i , index) in brand" :key="index">{{ i }}</h3>
   </div>
<h1> after Home component</h1>

 <!-- میخوام این کمپوننتم داخل تگ اصلی به یه اسم دیگ mount بشه -->
  <Teleport to="#forOtherComponent">
    
    <Mixins/>
  
  </Teleport>
  
</template>

<script>
import Home from "./components/Home.vue";
import Mixins from "./components/Mixins.vue";
import {Names} from "../src/mixins.js";

export default { 
  components: { Home , Mixins } , 

   mixins:[Names],
  
  data() {

    return {
  // متغیرآرایه
      // name:'data passed from App.vue',
      userInfo: {
        name:'saber',
        lastname: 'qadimi',
        age: 27
      },

      langs:['php' , 'laravel' , 'js' , 'go' , 'Vuejs'],
       brand: ['samsung' , 'Apple'],
      
    }
  }, 

   provide:{
       user: 'this is from App.vue of provide method',
     },

  methods: {
    showData(name){
      this.userInfo.name = name
    }
  },
  
  
  
  
  
  
  }

</script>

<style>
    #langs{
      color:red;
      background-color: lightblue;
      font-size: 26px;
      list-style: none;
      text-align: center;
    }
</style>
