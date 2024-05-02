<template>
    <div class="content">
        <div class="container py-5">
            <div class="row mb-5">
                <div class="col">
                    <div class="card">
                        <h2 class="text-center mt-5">RINCIAN BUKU</h2>
                        <div class="container mt-5">
                            <div class="row">
                                <div class="col-3 p-5">
                                    <img class="img-fluid" src="@/assets/img/cover1.jpg" alt="" style="width: 250px;">
                                </div>
                                <div class="col-8">
                                        <h4>Judul Buku : Bukan Aku Yang Dia Inginkan </h4>
                                        <h4>Tahun Terbit : 10 februari 2022 </h4>
                                        <h4>Penerbit : Cloudbooks Publishing</h4>
                                        <h4>RAK: - </h4>
                                        <h4>Kategori: Novel </h4>
                                        <h4>Deskripsi Buku : seorang wanita yang beranama Aiza Humairah, gadis salehah yang menyukai laki-laki bernama Fakhri Alfarazel dalam diam. Lelaki tampan yang memiliki prestasi membanggakan.tidak ada yang tahu perasaan ke fakhri kecuali dirinya dan Allah.</h4>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="row justify-content-end">
                <div class="col-1">
                    <nuxt-link to="/buku" class="row">
                        <button type="submit" class="btn justify-content-center btn-light btn-lg mr">BACK</button>
                    </nuxt-link>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup>
</script>

<style scoped>
.content{
    background-color: #5AAAC3;
}
.card {
    background-color: #AEDAE9;
    border-radius: 25px;
}

</style>