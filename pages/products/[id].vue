<template>
  <!-- breadcrumb -->
  <div class="container mt-3">
    <nav aria-label="breadcrumb">
      <ol class="breadcrumb">
        <li class="breadcrumb-item"><NuxtLink to="/">Home</NuxtLink></li>
        <li class="breadcrumb-item active" aria-current="page">
          Details figure
        </li>
      </ol>
    </nav>
  </div>
  <!-- end breadcrumb -->

  <!-- deskripsi produk -->
  <form action="cart.php" method="POST">
    <div class="container mt-3 detailProduk">
      <div class="row">
        <div
          class="col-sm-12 col-md-12 col-lg-12 col-xl-6 text-md-center text-lg-center text-xl-start"
        >
          <img
            :src="'/image/' + products.fotoProduk"
            :alt="products.namaProduk"
          />
          <input type="hidden" name="fotoProduk" value="" />
        </div>
        <div
          class="col-sm-12 col-md-12 col-lg-12 col-xl-6 text-md-center text-lg-center text-xl-start"
        >
          <h1 class="namaFigure">
            {{ products.namaProduk }}
          </h1>
          <h3 class="hargaProduk mt-3 mb-3 fw-bold">
            IDR {{ Intl.NumberFormat().format(products.harga) }}
          </h3>
          <p class="aboutProduk fw-light">
            Nama Produk : <br />
            <span class="fw-bold fs-6">
              {{ products.namaProduk }}
            </span>
          </p>
          <p class="aboutProduk fw-light">
            Series : <br />
            <span class="fw-bold fs-6">
              {{ products.series }}
            </span>
          </p>
          <p class="aboutProduk fw-light">
            Manufacture : <br />
            <span class="fw-bold fs-6">
              {{ products.manufacture }}
            </span>
          </p>
          <p class="aboutProduk fw-light">
            tinggi : <br />
            <span class="fw-bold fs-6">
              {{ products.tinggi }}
            </span>
          </p>
          <hr />
          <NuxtLink to="/cart"
            ><button
              class="btn btn-warning btn-keranjang"
              type="submit"
              name="btn-cart"
            >
              Tambah ke Keranjang!
            </button></NuxtLink
          >
        </div>
      </div>
    </div>
  </form>
  <!-- end deskripsi produk -->

  <!-- rekomendasi produk lain -->
  <div class="otherRecommendation mt-5 mb-5">
    <div class="container">
      <h1 class="titleRecommendation text-capitalize fw-bold mb-4">
        Other recommendation <br />
        maybe that you like
      </h1>
      <div class="row">
        <div
          class="figure col-sm-12 col-md-6 col-lg-6 col-xl-3 d-flex justify-content-center mb-3"
          v-for="p in listProducts
            .filter((p) => p.status === 'ready stock')
            .slice(0, 4)"
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
            <h3 class="hargaFigure mt-3 fw-bold">
              IDR {{ Intl.NumberFormat().format(p.harga) }}
            </h3>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const { id } = useRoute().params;

// fetch data from json file (multiple)

const uri =
  "https://my-json-server.typicode.com/raflyhmk/json-figuartz/products/" + id;

// fetch data from json file (single)
const { data: listProducts } = await useFetch(
  "https://my-json-server.typicode.com/raflyhmk/json-figuartz/products"
);

const { data: products } = await useFetch(uri);

console.log(listProducts.value);
console.log(products.value);
</script>

<style></style>
