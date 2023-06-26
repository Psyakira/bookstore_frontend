<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
      <a class="navbar-brand">Bookira'Store</a>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="/">Dashboard</a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="/koleksi">koleksi</a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="/anggota">Anggota</a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="/about">About</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
<RouterView/>
  <p class="fixed-bottom">CopyRight by Syakira</p>
</template>

<script>
export default {
  name: "NavBar"
}
</script>

<style scoped>

</style>