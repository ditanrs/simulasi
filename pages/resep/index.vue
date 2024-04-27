<script setup>
const supabase = useSupabaseClient();
const { data: reseps, refresh } = useAsyncData("resep", async () => {
  const { data, error } = await supabase.from("tbl_resep").select().order("id", { ascending: false });
  if (error) throw error;
  return data;
});

const form = ref({
  no_resep: "",
  tgl_resep: "",
  nama_pasien: "",
  nama_dokter: "",
  nama_obat: "",
  jumlah: "",
});
const kirimData = async () => {
  const { error } = await supabase.from("tbl_resep").insert([form.value]);
  if (error) throw error;
  else refresh();
};
</script>
<template>
  <div class="container-fluid">
    <div class="text-center mb-5">
      <h3>KELOLA RESEP</h3>
    </div>
    <div class="card">
      <form @submit.prevent="kirimData">
        <div class="mb-3 mt-5 container">
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input v-model="form.no_resep" type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="No resep" />
            </div>
            <div class="col-lg-6 pt-2">
              <input v-model="form.tgl_resep" type="date" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Tanggal" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input v-model="form.nama_pasien" type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Nama Pasien" />
            </div>
            <div class="col-lg-6 pt-2">
              <input v-model="form.nama_dokter" type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Nama Dokter" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6 pt-2">
              <input v-model="form.nama_obat" type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Nama Obat" />
            </div>
            <div class="col-lg-6 pt-2">
              <input v-model="form.jumlah" type="text" class="form-control form-control-lg border-dark rounded-2 me-5 mb-2" placeholder="Jumlah obat" />
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
                <td>No resep</td>
                <td>Tanggal</td>
                <td>Nama Pasien</td>
                <td>Nama Dokter</td>
                <td>Nama Obat</td>
                <td>Jumlah Obat</td>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(resep, i) in reseps" :key="i">
                <td>{{ resep.no_resep }}</td>
                <td>{{ resep.tgl_resep }}</td>
                <td>{{ resep.nama_pasien }}</td>
                <td>{{ resep.nama_dokter }}</td>
                <td>{{ resep.nama_obat }}</td>
                <td>{{ resep.jumlah}}</td>
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
