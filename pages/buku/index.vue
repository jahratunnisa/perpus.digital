<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">Cari Buku</h2>
        <div class="row d-flex justify-content-center my-3">
          <div class="input-group flex-nowrap rounded" style="width: 50rem">
            <input
              type="search"
              class="form-control"
              placeholder="Cari..."
              aria-label="Search"
              style="background-color: #6badc2"
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
        <h2 class="my-3 text-muted fw-bold">Koleksi Buku</h2>
        <div class="row">
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img
                  src="~/assets/img/cover3.jpg"
                  class="cover"
                  alt="cover 1"
                  style="width: 100%"
                />
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img
                  src="~/assets/img/cover2.jpg"
                  class="cover"
                  alt="cover 2"
                  style="width: 100%"
                />
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <nuxt-link to="/rincian/buku1">
                  <img
                    src="@/assets/img/cover1.jpg"
                    class="cover"
                    alt="cover 1"
                    style="width: 100%"
                  />
                </nuxt-link>
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img
                  src="~/assets/img/cover4.jpg"
                  class="cover"
                  alt="cover 4"
                  style="width: 100%"
                />
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
  height: 27em;
  padding: 0;
}
.cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: 0 30;
}
</style>
