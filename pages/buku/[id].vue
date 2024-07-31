<template>
    <div class="content">
        <div class="container-fluid">
            <nuxt-link to="/buku">
                <button type="button" class="btn btn-outline-dark btn-lg mt-4">KEMBALI</button></nuxt-link>
            <h2 class="text-center my-4 fw-bold">{{ buku?.judul }}</h2>
            <div class="row gy-5 d-flex justify-content-center flex-md-wrap">
                <div class="col-lg-3 col-auto">
                    <img :src="buku?.cover" class="cover row img-fluid" alt="cover buku" style="width: 250px;">
                </div>
                <div class="col-8">
                    <!-- <div class="row">
                        <h2 class="text start text-center my-4 fst-italic fw-bold"></h2>
                    </div> -->
                    <h3>PENULIS: {{ buku?.penulis }}</h3>
                    <h3>PENERBIT: {{ buku?.penerbit }}</h3>
                    <h3>TAHUN TERBIT: {{ buku?.tahun_terbit }}</h3>
                    <h3>RAK: {{ buku?.rak }}</h3>
                    <h3>KATEGORI: {{ buku?.kategori_buku?.nama }}</h3>
                    <h3>DESKRIPSI: {{ buku?.deskripsi }}</h3>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.row d-flex justify-content-center flex-md-wrap {
    padding-top: 180px;
}

@media screen and (max-width: 430px) {

    .row h3 {
        font-size: 15px;
    }


    .row d-flex justify-content-center flex-md-wrap {
        padding-top: 0px;
    }

}
</style>


<script setup>
import { onMounted } from 'vue';

const supabase = useSupabaseClient()
const route = useRoute()
const buku = ref()
const kategories = ref([])

const getBookByid = async () => {
    const { data, error } = await supabase
        .from('buku')
        .select(`*, kategori_buku(*)`)
        .eq('id', route.params.id)
        .maybeSingle()
    if (error) throw error
    if (data) buku.value = data
}

const getKategori = async () => {
    const { data, error } = await supabase
        .from('kategori_buku')
        .select('*')
    if (data) kategories.value = data
}

onMounted(() => {
    getBookByid()
    getKategori()
})

</script>