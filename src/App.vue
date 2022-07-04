<template>
  <div>
    <!-- پاس دادن دیتا بصورت آرایه -->
    <!-- <Home :user-name="name"/> -->
    <!-- پاس دادن دیتا بصورت آبجکت -->
    <!-- <Home :user-data="userInfo" /> -->

    <!-- دریافت دیتا از کلاس فرزند -->
   <Home :user-data="userInfo"  @emitChild="showData($event)" />
  
   <h1>App.vuejs</h1>

  </div>
</template>

<script>
import Home from "./components/Home.vue";

export default { 
  components: { Home } , 
  data() {
    return {
      // متغیرآرایه
      // name:'data passed from App.vue',
      userInfo: {
        name:'saber',
        lastname: 'qadimi',
        age: 27
      }
    }
  }, 
  methods: {
    showData(name){
      this.userInfo.name = name
    }
  },
  
  
  
  
  
  
  }

</script>

<style>

</style>
