<script setup>
const supabase = useSupabaseClient();
const logs = ref([]);

async function getLog() {
  const { data, error } = await supabase.from("log_act").select(`*, users(username)`);
  if (error) throw error;
  if (data) logs.value = data;
}
onMounted(() => {
  getLog();
});
</script>
<template>
  <div class="container-fluid">
    <div class="text-center mt-5 mb-4">
      <h3>Log Activity</h3>
    </div>

    <div class="card">
      <div class="row">
        <div class="col-lg-12 d-flex justify-content-center">
          <table class="table">
            <thead class="table-dark">
              <tr>
                <td>No</td>
                <td>username</td>
                <td>Tanggal</td>
                <td>aktivitas</td>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(log, index) in logs">
                <td value="#">{{ index + 1 }}</td>
                <td>{{ log.users.username }}</td>
                <td>{{ log.tanggal }}</td>
                <td>{{ log.aktifitas }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  margin-bottom: 2%;
  box-shadow: 5px 5px 5px #888888;
}

table {
  width: 70%;
  margin-top: 1%;
}
</style>
