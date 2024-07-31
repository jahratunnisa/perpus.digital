<template>
  <div class="container-fluid">
    <div class="row mt-3">
      <div class="col">
        <button class="btn btn-secondary" @click="navigateTo('/home')">Kembali</button>
      </div>
    </div>
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
        <div class="row d-flex justify-content-center my-3">
          <div class="input-group flex-nowrap rounded" style="width: 50rem">
            <input
              type="search"
              class="form-control"
              placeholder="Cari..."
              aria-label="Search"
              style="background-color: #6badc2"
              v-model="keyword"
              @input="getPengunjung"
            />
            <span class="input-group-text" style="background-color: #6badc2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                fill="currentColor"
                class="bi bi-search"
                viewBox="0 0 16 16"
              >
                <path
                  d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"
                />
              </svg>
            </span>
          </div>
        </div>
        <div class="table-responsive">
          <table class="table">
            <thead>
              <tr>
                <td>NO</td>
                <td>NAMA</td>
                <td>KATEGORI</td>
                <td>KELAS LENGKAP</td>
                <td>KEPERLUAN</td>
                <td>WAKTU/TGL</td>
              </tr>
            </thead>
            <tbody>
                <tr v-for="(visitors,i) in visitors" :key="i" class="text-center fst-italic">
                  <td>{{ i+1 }}.</td>
                  <td>{{ visitors.nama }}</td>
                  <td>{{ visitors.keanggotaan.nama }}</td>
                  <td>{{ visitors.tingkat}}-{{ visitors.jurusan }}{{ visitors.kelas }}</td>
                  <td>{{ visitors.keperluan.nama }}</td>
                  <td>{{ visitors.tanggal }}/{{ visitors.waktu.split(".")[0] }} </td>
                </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const supabase= useSupabaseClient()

const keyword = ref('')
const visitors = ref([])
const jmlpengunjung= ref(0)

const getPengunjung =async () => {
  const { data, error } = await supabase
  .from('pengunjung')
  .select(`*, keanggotaan(*), keperluan(*)`)
  .ilike("nama",`%${keyword.value}%`)
  .order('id', { ascending: false})
  if (error) throw error
  if(data) visitors.value = data
}

const getJmlPengunjung = async () => {
  const{ data, count } = await supabase
    .from("pengunjung") 
    .select('*', { count: "exact" })
    if(data) jmlpengunjung.value = count
}

onMounted(() =>{
  getPengunjung()
  getJmlPengunjung()
})

</script>

<style scoped>
.table td {
  background: none;
  border: 1px solid black;
}
</style>