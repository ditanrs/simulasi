<script setup>
const supabase = useSupabaseClient();

async function logout() {
  const { error } = await supabase.auth.signOut();
  if (!error) navigateTo("/Login");
}

async function insertLog() {
  const user = useSupabaseUser();
  const { error } = await supabase.from("log_act").insert({
    aktifitas: "Logout",
    id_user: user.value.id,
  });
  if (error) throw error;
  if (!error) logout();
}
onMounted(() => {
  insertLog();
});
</script>

<template>
  <div class="container-fluid">
    <h3 class="text-center">Anda sedang keluar dari aplikasi ini</h3>
    <h3 class="text-center">Loading...</h3>
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
