<template>
  <!-- search & title -->
  <div class="container mt-4">
    <div class="row">
      <div class="col-8">
        <h1 class="title">Daftar produk</h1>
      </div>
      <div class="col-4">
        <form
          class="form-inline search-form d-flex justify-content-end"
          action=""
          method="get"
        >
          <input
            class="form-control me-4"
            type="search"
            name="cari"
            placeholder="Search"
            aria-label="Search"
          />
          <button
            class="btn btn-outline-primary btn-search my-2 my-sm-0"
            type="submit"
          >
            search
          </button>
        </form>
      </div>
    </div>
  </div>
  <!-- end search & title -->

  <!-- list produk -->
  <div class="container mt-3">
    <div class="row">
      <div
        class="figure col-sm-12 col-md-6 col-lg-6 col-xl-3 d-flex justify-content-center mb-3"
        v-for="p in products"
        :key="p"
      >
        <NuxtLink :to="`/products/${p.id}`" style="text-decoration: none"
          ><center>
            <img
              :src="'/image/' + p.fotoProduk"
              alt="action figure vladilena milize"
            />
          </center>
          <h1 class="namaFigure fw-medium mt-2">
            {{ p.namaProduk }}
            <span
              style="font-weight: 700; color: #9a7b41"
              class="text-capitalize"
            >
              ({{ p.status }})</span
            >
          </h1>
          <h3 class="hargaFigure mt-3 fw-bold">IDR {{ p.harga }}</h3>
        </NuxtLink>
      </div>
    </div>
  </div>
  <!-- end list produk -->
</template>

<script setup>
// fetch data from json file
const { data: products } = await useFetch(
  "https://my-json-server.typicode.com/raflyhmk/json-figuartz/products"
);
</script>

<style></style>
