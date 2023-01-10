<template>
  <div class="flex flex-wrap justify-start">
    <div v-for="item in data" :key="item.id">
      <user-side :dataItem="item"></user-side>
    </div>
  </div>
</template>

<script>
import UserSide from "./UsersSide";

export default {

  props:['data'],

  
  components: {
    UserSide,
  },
 
  methods: {},

  
};
</script>

<style></style>
