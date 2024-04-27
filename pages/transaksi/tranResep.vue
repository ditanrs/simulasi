<template>
  <div class="container-fluid">
    <div class="text-center mb-5">
      <h3>TRANSAKSI RESEP</h3>
    </div>
    <div class="card">
      <form>
        <div class="mb-3 mt-5 container">
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="No transaksi" />
            </div>
            <div class="col-lg-6 pt-2">
              <input type="date" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Tanggal" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="No resep" />
            </div>
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Nama Pasien" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Nama Obat" />
            </div>
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Jumlah obat" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Total Bayar" />
            </div>
          </div>
        </div>
        <div class="col-lg-12 d-flex justify-content-center mb-2">
          <button type="submit" class="btn btn-success bg-success text-white rounded-2 px-4">KIRIM</button>
        </div>
      </form>
    </div>
    <div class="card">
      <div class="row">
        <div class="col-lg-12 d-flex justify-content-center">
          <table class="table">
            <thead class="table-dark">
              <tr>
                <td>No Transaksi</td>
                <td>Tanggal</td>
                <td>No resep</td>
                <td>Nama pasien</td>
                <td>Nama obat</td>
                <td>Jumlah obat</td>
                <td>total</td>
                
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
