<template>
  <div class="container-fluid">
    <div class="text-center mb-5">
      <h3>KELOLA USER</h3>
    </div>
    <div class="card">
      <form>
        <div class="mb-3 mt-5 container">
          <div class="row">
            <div class="col-lg-6 pt-2">
              <select class="form-control form-control-lg form-select border-dark rounded-2 me-5 mb-2">
                <option>Tipe User</option>
                <option>Admin</option>
                <option>Apoteker</option>
                <option>Kasir</option>
              </select>
            </div>
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Username" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input type="email" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Email" />
            </div>
            <div class="col-lg-6 pt-2">
              <input type="password" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Password" />
            </div>
          </div>
        </div>
        <div class="col-lg-12 d-flex justify-content-center mb-2">
          <button type="submit" class="btn btn-success bg-success text-white rounded-2 px-4">Tambah</button>
        </div>
      </form>
    </div>
    <div class="card">
      <div class="row">
        <div class="col-lg-12 d-flex justify-content-center">
          <table class="table">
            <thead class="table-dark">
              <tr>
                <td>Tipe User</td>
                <td>username</td>
                <td>Email</td>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td></td>
                <td></td>
                <td></td>
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
table {
  width: 70%;
  margin-top: 1%;
}
.card {
  margin-bottom: 2%;
  box-shadow: 5px 5px 5px #8888;
}
</style>
