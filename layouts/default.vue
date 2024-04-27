<script setup>
const user = useSupabaseUser();
</script>
<template>
  <div>
    <div class="container-fluid p-0">
      <span v-if="user">
        <Header v-if="user.user_metadata.tipe_user === 'admin'" />
        <HeaderA v-if="user.user_metadata.tipe_user === 'apoteker'" />
        <HeaderK v-if="user.user_metadata.tipe_user === 'kasir'" />
      </span>
      <slot />
    </div>
  </div>
</template>
