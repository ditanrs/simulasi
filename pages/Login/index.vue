<script setup>
definePageMeta({
  layout: "login",
});
const supabase = useSupabaseClient();
const email = ref("");
const password = ref("");

async function handleLogin() {
  const { data, error } = await supabase.auth.signInWithPassword({
    email: email.value,
    password: password.value,
  });
  if (data) {
    const user = useSupabaseUser();
    insertLog(user);
    navigateTo("/");
  }
  if (error) throw error;
}

async function insertLog(user) {
  const { error } = await supabase.from("log_act").insert({
    aktifitas: "Login",
    id_user: user.value.id,
  });
  if (error) throw error;
}
</script>

<template>
  <div class="logo1">
    <div class="container-fluid">
      <div>
        <img src="assets/img/logo.png" alt="logo" class="logo" />
        <h1>APOTEX XYZ</h1>
      </div>

      <form @submit.prevent="handleLogin">
        <input v-model="email" type="email" class="form-control form-control-lg rounded-2 border-dark" placeholder="email" />
        <br />
        <input v-model="password" type="password" class="form-control form-control-lg rounded-2 border-dark" placeholder="password" />
        <br />
        <button type="submit" class="btn btn-success text-white rounded-2 px-4 text-center">LOGIN</button>
      </form>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 35%;
}
.logo1 {
  background-color: #87bc9c;
}
.form-control {
  width: 100%;
}
h1 {
  margin-top: 15px;
  margin-bottom: 20px;
}
.logo {
  width: 95px;
  margin-left: 30%;
}
button {
  background-color: #019901 !important;
}
</style>
