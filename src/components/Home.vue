<template>
  <!-- نمایش دیتا از App.vue به کمک
     متود provide.inject -->
  <h2>{{ user }}</h2>
  <!-- نمایش دیتا همراه با html -->
   <slot name="ul"></slot>
   <hr>
  <!-- نمایش دادن دیتا بصورت آرایه -->
  <!-- <h1>{{userName}}</h1> -->
  <ul>
    <li>{{ userData.name }}</li>
    <li>{{ userData.lastname }}</li>
    <li>{{ userData.age }}</li>
  </ul>

  <button @click="sendData">send Data for App.vue</button>
</template>

<script>
export default {
  name: 'TodoItem',
  //  گرفتن دیتا بصورت آرایه
  //    props:['userName']
  //  گرفتن دیتا بصورت آبجکت
  props: {
    userData: Object,
  },

  inject: ['user'],

  data() {
    return {
      name: 'JustLearn',
    }
  },

  methods: {
    sendData() {
      this.$emit('emitChild', this.name)
    },
  },
}
</script>

<style scoped>
ul {
  background-color: beige;
  padding: 6px;
  text-align: center;
  list-style: none;
}
li {
  color: blue;
  padding-top: 10px;
  font-size: 22px;
}
</style>
