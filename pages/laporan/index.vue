<template>
  <div class="container-fluid">
    <div class="text-center mt-5">
      <h3>KELOLA LAPORAN</h3>
    </div>
    <h5 class="ms-5">Lapporan Penjualan</h5>
    <div>
      <div class="card">
        <div class="row g-3 mt-1 mb-1 ms-5 justify content-center">
          <div class="col-auto">
            <label class="col-form-label">Dari tanggal</label>
          </div>
          <div class="col-auto">
            <input type="date" class="form-control" aria-describedby="passwordHelpInline" />
          </div>
          <div class="col-auto">
            <label class="col-form-label">Dari tanggal</label>
          </div>
          <div class="col-auto">
            <input type="date" class="form-control" aria-describedby="passwordHelpInline" />
          </div>
          <button type="button" class="btn btn-outline-dark rounded-1">Apply</button>
        </div>
      </div>
    </div>
    <div class="card">
      <div class="row">
        <div class="col-lg-12 d-flex justify-content-center">
          <table class="table">
            <thead class="table-dark">
              <tr>
                <td>Tanggal Transaksi</td>
                <td>Total bayar</td>
              </tr>
            </thead>
            <tbody>
              <tr>
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
button {
  width: 10%;
  margin-left: 10px;
  background-color: #d3d1d1;
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
