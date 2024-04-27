<script setup>
const supabase = useSupabaseClient();
const { data: obats, refresh } = useAsyncData("obat", async () => {
  const { data, error } = await supabase.from("tbl_obat").select().order("id", { ascending: false });
  if (error) throw error;
  return data;
});

const form = ref({
  kode_obat: "",
  nama_obat: "",
  expired_date: "",
  jumlah: "",
  harga: "",
});
const kirimData = async () => {
  const { error } = await supabase.from("tbl_obat").insert([form.value]);
  if (error) throw error;
  else refresh();
};
</script>

<template>
  <div class="container-fluid">
    <div class="text-center mb-5">
      <h3>KELOLA OBAT</h3>
    </div>
    <div class="card">
      <form @submit.prevent="kirimData">
        <div class="mb-3 mt-3 container">
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input v-model="form.kode_obat" type="number" class="form-control form-control-lg rounded-2 border-dark" placeholder="Kode Obat" />
            </div>
            <div class="col-lg-6 pt2">
              <input v-model="form.nama_obat" type="text" class="form-control form-control-lg rounded-2 border-dark" placeholder="Nama Obat" />
            </div>
          </div>

          <div class="row">
            <div class="col-lg-6 pt-2">
              <input v-model="form.expired_date" type="date" class="form-control form-control-lg rounded-2 border-dark" placeholder="Expired Date" />
            </div>

            <div class="col-lg-6 pt-2">
              <input v-model="form.jumlah" type="number" class="form-control form-control-lg rounded-2 border-dark" placeholder="Jumlah" />
            </div>
          </div>
          <div class="col-lg-6 pt-2">
            <input v-model="form.harga" type="number" class="form-control form-control-lg rounded-2 border-dark" placeholder="Harga" />
          </div>
        </div>
        <div class="col-lg-12 justify-content-center d-flex">
          <button type="submit" class="btn btn-success text-white bg-success rounded-2 px-4 text-center mb-5">Tambah</button>
        </div>
      </form>
    </div>

    <div>
      <div class="card">
        <div class="row">
          <div class="col-lg-12 d-flex justify-content-center">
            <table class="table">
              <thead class="table-dark">
                <tr>
                  <td>Kode Obat</td>
                  <td>Nama Obat</td>
                  <td>Expired Date</td>
                  <td>Jumlah</td>
                  <td>Harga</td>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(obat, i) in obats" :key="i">
                  <td>{{ obat.kode_obat }}</td>
                  <td>{{ obat.nama_obat }}</td>
                  <td>{{ obat.expired_date }}</td>
                  <td>{{ obat.jumlah }}</td>
                  <td>{{ obat.harga }}</td>
                </tr>
              </tbody>
            </table>
          </div>
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
