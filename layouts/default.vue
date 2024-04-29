<template>
  <div class="container-fluid">
    <Header />
    <slot />
  </div>
</template>

<style>
.bg-primary {
  background-color: #81C3D8 !important;
}

body {
  background: transparent url("~/assets/img/bg-app.jpg") no-repeat center center
    fixed;
  background-size: cover;
}
</style>