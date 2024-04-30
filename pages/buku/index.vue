<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4 ">Cari Buku</h2>
                <div class="my-3 d-flex justify-content-center">
                    <input type="search" class="col-sm-10 form-control" placeholder="Cari buku" style="background-color: #6BADC2; width: 50rem;">
                </div>
                <h2 class="my-3 text-muted">Koleksi Buku</h2>
                <div class="row">
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <img src="~/assets/img/cover3.jpg" class="cover" alt="cover 1" style="width: 100%;">
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <img src="~/assets/img/cover2.jpg" class="cover" alt="cover 2" style="width: 100%;">

                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <img src="~/assets/img/cover1.jpg" class="cover" alt="cover 3" style="width: 100%;">
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <img src="~/assets/img/cover4.jpg" class="cover" alt="cover 4" style="width: 100%;">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.card-body {
    width: 100%;
    height: 20em;
    padding: 0;
}
.cover {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: 0 30;
}
</style>
