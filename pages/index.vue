<script setup>
const users = useSupabaseUser();
console.log(users.value?.user_metadata.tipe_user);
</script>
<template>
  <div class="container-fluid">
    <h3 class="text-center">SELAMAT DATANG DI APOTEK XYZ</h3>
    <h4 v-if="users" class="text-center">Anda Adalah {{ users.user_metadata.tipe_user }}</h4>
  </div>
</template>
<style scoped>
.container-fluid {
  background-image: url("assets/img/bg.jpg");
  height: 85vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
