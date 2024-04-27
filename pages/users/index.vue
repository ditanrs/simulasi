<script setup>
// definePageMeta({
//   layout: "main",
//   middleware: "auth",
// });

const supabase = useSupabaseClient();
const user = useSupabaseUser();

const form = ref({
  tipe_user: "",
  username: "",
  email: "",
  password: "",
});

async function tambahUser() {
  const { data, error } = await supabase.auth.signUp({
    email: form.value.email,
    password: form.value.password,
    options: {
      data: {
        tipe_user: form.value.tipe_user,
        username: form.value.username,
      },
    },
  });
  if (error) throw error;
  if (data) {
    insertUser();
  }
}
async function insertUser() {
  const { error } = await supabase.from("users").insert({
    id: user.value.id,
    tipe_user: form.value.tipe_user,
    username: form.value.username,
    email: form.value.email,
    password: form.value.password,
  });
  if (error) throw error;
  if (data) navigateTo("/Login");
}
</script>

<template>
  <div class="container-fluid">
    <div class="text-center mb-5">
      <h3>KELOLA USER</h3>
    </div>
    <div class="card">
      <div class="mb-5">
        <form @submit.prevent="tambahUser">
          <div class="mb-3 mt-5 container">
            <div class="row">
              <div class="col-lg-6 pt-2">
                <select v-model="form.tipe_user" class="form-control form-control-lg form-select rounded-2 border-dark me-5 mb-2">
                  <option value="">Tipe User</option>
                  <option value="admin">Admin</option>
                  <option value="apoteker">Apoteker</option>
                  <option value="kasir">Kasir</option>
                </select>
              </div>
              <div class="col-lg-6 pt2">
                <input v-model="form.username" type="text" class="form-control form-control-lg rounded-2 border-dark me-5 mb-4" placeholder="Username" />
              </div>
            </div>

            <div class="row">
              <div class="col-lg-6 pt-2">
                <input v-model="form.email" type="email" class="form-control form-control-lg rounded-2 border-dark me-5" placeholder="Email" />
              </div>

              <div class="col-lg-6 pt-2">
                <input v-model="form.password" type="password" class="form-control form-control-lg rounded-2 border-dark" placeholder="Password" />
              </div>
            </div>
          </div>
          <div class="col-lg-12 justify-content-center d-flex">
            <button type="submit" class="btn btn-success text-white bg-success rounded-2 px-4 text-center">Tambah</button>
          </div>
        </form>
      </div>
    </div>
    <div class="card">
      <div class="row">
        <div class="col-lg-12 justify-content-center d-flex">
          <table class="table">
            <thead class="table-dark">
              <tr>
                <td>Tipe User</td>
                <td>Username</td>
                <td>Email</td>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(user, index) in users">
                <td>{{ user.user_metadata.tipe_user }}</td>
                <td>{{ user.user_metadata.username }}</td>
                <td>{{ user.user_metadata.email }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container-fluid {
  margin-top: 2%;
}
.bg-success {
  background-color: #019901 !important;
}

table {
  width: 70%;
  margin-top: 1%;
}

.card {
  margin-bottom: 2%;
  box-shadow: 5px 5px 5px #888888;
}
</style>
