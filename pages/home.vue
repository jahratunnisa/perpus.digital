<template>
  <div class="container-fluid">
    <div class="row mt-3">
      <nuxt-link to="/" class="col">
        <button class="btn btn-primary" >Isi Kunjungan</button>
      </nuxt-link>
    </div>
    <div class="row my-5 gy-3">
      
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung">
          <div class="card bg-pengunjung rounded-5 bg-primary">
            <div class="card-body">
              <h2 class="text-light">Pengunjung</h2>
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card bg-buku rounded-5 bg-primary">
            <div class="card-body">
              <h2 class="text-light">Cari Buku</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
    <h2>STATISTIK</h2>
    <div class="row py-5 gy-3">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung">
          <div class="card pengunjung rounded-5 st">
            <div class="card-body">
              <h1 class="text-center" style="margin-top: 80px;">{{ totalPengunjung }} PENGUNJUNG</h1>
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card buku rounded-5 st">
            <div class="card-body">
              <h1 class="text-center" style="margin-top: 80px;">{{ totalBuku }} BUKU</h1>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()

const totalPengunjung = ref(0)
const totalBuku = ref(0)

const getTotalPengunjung = async () => {
  const { count, error } = await supabase
    .from('pengunjung')
    .select('*', { count: 'exact', head: true })
  if (error) throw error
  if (count) totalPengunjung.value = count
}

const getTotalBuku= async () => {
  const { count, error } = await supabase
    .from('buku')
    .select('*', { count: 'exact', head: true })
  if (error) throw error
  if (count) totalBuku.value = count
}

onMounted(() => {
  getTotalPengunjung()
  getTotalBuku()
})
</script>

<style scoped>
.card {
  height: 250px;
  box-shadow: 1px 1px 10px #424242;

}

.card.bg-pengunjung {
  background-image: url("@/assets/img/kunjungan.jpeg");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}

.card.bg-buku {
  background: url("@/assets/img/caribuku.jpg") no-repeat center center;
  background-size: cover;
}

.st {
  background-color: #7ac4dd92;
}
</style>