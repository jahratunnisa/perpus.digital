<!-- <template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">ISI BUKU KUNJUNGAN</h2>
        <form>
          <div class="row">
            <div class="col-md-8">
              <div class="mb-3">
                <input
                  type="text"
                  class="form-nama form-control form-control-lg rounded-5"
                  placeholder="NAMA"
                />
              </div>
              <div class=" mb-3">
                <select
                  class="form-kategori form-control form-control-lg form-select round-5"
                >
                  <option value="">KATEGORI</option>
                  <option value="siswa">siswa</option>
                  <option value="Guru">Guru</option>
                  <option value="staf">Staf</option>
                  <option value="umum">Umum</option>
                </select>
              </div>
              <div class="mb-3">
                <select
                  class="form-keperluan form-control form-control-lg form-select rounded-5"
                >
                  <option value="">KEPERLUAN</option>
                  <option value="baca">Baca Buku</option>
                  <option value="Pinjam">Pinjam Buku</option>
                  <option value="kembalikan">kembalikan buku</option>
                </select>
              </div>


            <div class="grup-option">
              <div class="col-lg">
                <select
                  class="option-jurusan form-control form-control-lg form-select rounded-5 mb-2"
                >
                  <option value="">JURUSAN</option>
                  <option value="PPLG">PPLG</option>
                  <option value="TKJT">TKJT</option>
                  <option value="TSM">TSM</option>
                  <option value="DKV">DKV</option>
                  <option value="TOI">TOI</option>
                </select>
              </div>

              <div class="col-lg">
                <select
                  class="option-tingkat form-control form-control-lg form-select rounded-5 mb-2"
                >
                  <option value="">TINGKAT</option>
                  <option value="X">X</option>
                  <option value="XI">XI</option>
                  <option value="XII">XII</option>
                </select>
              </div>

              <div class="col-lg">
                <select
                  class="option-kelas form-control form control-lg form-select rounded-5 mb-2"
                >
                  <option value="">KELAS</option>
                  <option value="1">1</option>
                  <option value="2">2</option>
                  <option value="3">3</option>
                </select>
              </div>
            </div>


            </div>
            <div class="col-md-4">
              <img
                src="~/assets/img/img-kunjungan.png"
                alt="gambar tambah kunjungan"
              />
              
          <button type="submit" class="btn justify-content-center btn-light btn-lg rounded-5 px-5 mr">
            SUBMIT
          </button>
            </div>
          </div>
          <div class="mb-3">
            <div class="row">
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>


<style scoped>
.form-control {
  background-color: #ace9fc !important;
  border-radius: 40px;
}

.form-nama{
  height: 70px;
  font-size: large;
  font-weight: 700;
  color: black;
}

.form-keperluan{
  height: 70px;
  font-size: large;
  font-weight: 700;
}

.form-kategori{
  height: 70px;
  font-size: large;
  font-weight: 700;
}

.grup-option{
  display: grid;
  grid-template-columns: auto auto auto;
}

.option-tingkat{
  width: 100%;
  font-weight: 700;
}

.option-jurusan{
  width: 100%;
  font-weight: 700;

  
}

.option-kelas{
  width: 100%;
  font-weight: 700;
}

</style> -->


<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">ISI DATA KUNJUNGAN</h2>
        <form @submit.prevent="kirimData">
          <div class="row">
            <div class="col-md-8">
              <div class="mb-3">
                <input
                  type="text"
                  v-model="form.nama"
                  class="form-nama form-control form-control-lg rounded-5"
                  placeholder="NAMA"
                />
              </div>
              <div class=" mb-3">
                <select
                v-model="form.keanggotaan"
                  class="form-kategori form-control form-control-lg form-select round-5"
                >
                  <option value="">KATEGORI</option>
                  <option v-for="(member,i) in members" :key="i" :value="member.id">{{ member.nama }}</option>
                </select>
              </div>
              <div class="mb-3">
                <select
                v-model="form.keperluan"
                  class="form-keperluan form-control form-control-lg form-select rounded-5"
                >
                  <option value="">KEPERLUAN</option>
                  <option v-for="(item,i) in objectives" :key="i" :value="item.id">{{ item.nama }}</option>
                </select>
              </div>


            <div v-if="keanggotaan == 'Siswa'" class="grup-option">
              <div class="col-lg">
                <select
                v-model="form.jurusan"
                  class="option-jurusan form-control form-control-lg form-select rounded-5 mb-2"
                >
                  <option value="">JURUSAN</option>
                  <option value="PPLG">PPLG</option>
                  <option value="TKJT">TKJT</option>
                  <option value="TSM">TSM</option>
                  <option value="DKV">DKV</option>
                  <option value="TOI">TOI</option>
                </select>
              </div>

              <div class="col-lg">
                <select
                v-model="form.tingkat"
                  class="option-tingkat form-control form-control-lg form-select rounded-5 mb-2"
                >
                  <option value="">TINGKAT</option>
                  <option value="X">X</option>
                  <option value="XI">XI</option>
                  <option value="XII">XII</option>
                </select>
              </div>

              <div class="col-lg">
                <select
                v-model="form.kelas"
                  class="option-kelas form-control form control-lg form-select rounded-5 mb-2"
                >
                  <option value="">KELAS</option>
                  <option value="1">1</option>
                  <option value="2">2</option>
                  <option value="3">3</option>
                </select>
              </div>
            </div>


            </div>
            <div class="col-md-4">
              <img
                src="~/assets/img/img-kunjungan.png"
                alt="gambar tambah kunjungan"
              />
              <nuxt-link to="/pengunjung/tambah">
          <button type="submit" class="btn justify-content-center btn-light btn-lg rounded-5 px-5 mr">
            SUBMIT
          </button></nuxt-link>
            </div>
          </div>
          <div class="mb-3">
            <div class="row">
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script setup>
const supabase = useSupabaseClient()

const members = ref([])
const objectives = ref([])

const form = ref({
  nama: "",
  keanggotaan: "",
  tingkat: "",
  jurusan: "",
  kelas: "",
  keperluan: "",
})

const kirimData = async () => {
  const { error } = await supabase.from('pengunjung').insert([form.value])
  if(!error) navigateTo('/pengunjung')
}

const getkeanggotaan = async () => {
  const { data, error } = await supabase.from('keanggotaan').select('*')
  if(data) members.value = data
}

const getkeperluan = async () => {
  const { data, error } = await supabase.from('keperluan').select('*')
  if(data) objectives.value = data
}

onMounted(() => {
  getkeanggotaan()
  getkeperluan()
})

</script>
<style scoped>
.form-control {
  background-color: #ace9fc !important;
  border-radius: 40px;
}

.form-nama{
  height: 70px;
  font-size: large;
  font-weight: 700;
  color: black;
}

.form-keperluan{
  height: 70px;
  font-size: large;
  font-weight: 700;
}

.form-kategori{
  height: 70px;
  font-size: large;
  font-weight: 700;
}

.grup-option{
  display: grid;
  grid-template-columns: auto auto auto;
}

.option-tingkat{
  width: 100%;
  font-weight: 700;
}

.option-jurusan{
  width: 100%;
  font-weight: 700;

  
}

.option-kelas{
  width: 100%;
  font-weight: 700;
}
</style>