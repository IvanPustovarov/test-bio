<script setup>
import ProfilePhoto from './components/ProfilePhoto.vue';
import Password from './components/Password.vue';
import PersonalData from './components/PersonalData.vue';
</script>

<template>
  <div class="container">
    <ProfilePhoto />
    <!-- <PersonalData/>
    <Password /> -->
  </div>
</template>

<style lang="scss" scoped>
  .container{
    display: flex;
  }
</style>
