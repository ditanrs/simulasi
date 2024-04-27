<template>
  <div class="container-fluid">
    <div class="text-center mb-5">
      <h3>KELOLA OBAT</h3>
    </div>
    <div class="card">
      <form>
        <div class="mb-3 mt-5 container">
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input type="number" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Kode obat" />
            </div>
            <div class="col-lg-6 pt-2">
              <input type="date" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Tanggal" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Nama obat" />
            </div>
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Jumlah" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Harga" />
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
                <td>Kode obat</td>
                <td>Expired date</td>
                <td>Nama obat</td>
                <td>Jumlah</td>
                <td>Harga</td>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td></td>
                <td></td>
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
