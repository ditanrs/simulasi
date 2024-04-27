<template>
  <div class="logo1">
    <div class="container-fluid">
      <div>
        <img src="assets/img/logo.png" alt="logo" class="logo" />
        <h1>APOTEK XYZ</h1>
      </div>
      <form>
        <input type="email" class="form-control form-control-lg rounded-2 border-dark" placeholder="email" />
        <br />
        <input type="password" class="form-control form-control-lg rounded-2 border-dark" placeholder="password" />
        <button type="submit" class="btn btn-success bg-success text-white rounded-2 px-4 mt-3">LOGIN</button>
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
