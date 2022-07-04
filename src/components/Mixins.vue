<template>
  <div>
    <ul>
      <li v-for="(user, index) in users" :key="index">{{ user }}</li>
    </ul>
  </div>
</template>

<script>
import {Names} from "../mixins.js";

export default {
  name: 'ThisMixinExample',
  mixins:[Names],

}
</script>

<style lang="scss" scoped></style>
