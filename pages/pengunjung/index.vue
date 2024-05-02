<template>
  <div class="container-fluid">
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
        <table class="table table-responsive">
          <thead>
            <tr>
              <td>NO</td>
              <td>NAMA</td>
              <td>KATEGORI</td>
              <td>KELAS/JURUSAN</td>
              <td>KEPERLUAN</td>
              <td>WAKTU/TGL</td>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>1.</td>
              <td>jahratunnisa</td>
              <td>Siswa</td>
              <td>XI PPLG3</td>
              <td>Baca</td>
              <td>11.00/13-04-2024</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>

  <!-- <table class="table">
    <thead>
    <tr>
        <th scope="col">#</th>
        <th scope="col">First</th>
        <th scope="col">Last</th>
        <th scope="col">Handle</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <th scope="row">1</th>
        <td>Mark</td>
        <td>Otto</td>
        <td>@mdo</td>
    </tr>
    <tr>
        <th scope="row">2</th>
        <td>Jacob</td>
        <td>Thornton</td>
        <td>@fat</td>
    </tr>
    <tr>
        <th scope="row">3</th>
        <td colspan="2">Larry the Bird</td>
        <td>@twitter</td>
    </tr>
    </tbody>
</table> -->
</template>

<style scoped>
.table td {
  background: none;
  border: 1px solid black;
}
</style>