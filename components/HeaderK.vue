<script setup>
const supabase = useSupabaseClient();
</script>
<template>
  <nav class="navbar bg-light">
    <div class="container-fluid">
      <div class="col-lg-1">
        <NuxtLink to="/">
          <img src="assets/img/logo.png" alt="logo" class="logo" />
        </NuxtLink>
      </div>
      <div class="col me-5">
        <h6>APOTEK XYZ</h6>
        <p>ADMIN</p>
      </div>

      <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbar" aria-controls="offcanvasNavbar">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="offcanvas offcanvas-end bg-dark" id="offcanvasNavbar" aria-labelledby="offcanvasNavbarLabel">
        <div class="row justify-content-center">
          <div class="col-md offset-md-2">
            <div class="offcanvas-header">
              <NuxtLink to="/">
                <img src="assets/img/kasir.png" alt="admin" />
              </NuxtLink>
            </div>
            <div class="d-grid gap-2 px-2">
              <div class="btn1">
                <NuxtLink to="/transaksi/tranObat" class="btn btn-light border-dark">Transaksi Obat</NuxtLink>
              </div>
              <div class="btn1">
                <NuxtLink to="/transaksi/tranResep" class="btn btn-light border-dark">Transaksi Resep</NuxtLink>
              </div>
              <NuxtLink class="btn btn-danger mt-3" to="/logout">Logout</NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.logo {
  width: 50px;
}

img {
  width: 70%;
}
.bg-light {
  background-color: #87bc9c !important;
}
.bg-dark {
  background-color: #b0ccbb !important;
}
.d-grid {
  width: 100%;
}
.btn {
  width: 70%;
}
nav {
  width: 100%;
  box-shadow: 0px 5px 5px #888888;
}
.offcanvas {
  width: 20%;
}
</style>
