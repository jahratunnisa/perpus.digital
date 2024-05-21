<!-- <template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung">
          <div class="card bg-pengunjung rounded-5 bg-primary">
            <div class="card-body">
              <h2 class="text-light">pengunjung</h2>
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
  </div>
</template>

<style scoped>
.card {
  height: 250px;
  box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
  background-image: url("../assets/img/kunjungan.jpeg");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}
.card.bg-buku {
  background: url("../assets/img/caribuku.jpg") no-repeat center center;
  background-size: cover;
}
</style>  -->
<template>
  <div class="container-fluid">
    <div class="row my-5">
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
    <div class="row py-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung">
          <div class="card pengunjung rounded-5 st">
            <div class="card-body">
              <h1 class="text-center" style="margin-top: 80px;"> 1 PENGUNJUNG</h1>
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card buku rounded-5 st">
            <div class="card-body">
              <h1 class="text-center" style="margin-top: 80px;">4 BUKU</h1>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script setup>


const keanggotaan = ref('')
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

.st{
  background-color: #7ac4dd92;
}
</style>