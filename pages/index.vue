<template>
  <!-- carousel header -->
  <section id="header" class="mb-3">
    <div
      id="carouselExampleInterval"
      class="carousel slide"
      data-bs-ride="carousel"
    >
      <div class="carousel-inner">
        <div class="carousel-item active" data-bs-interval="2000">
          <img
            src="/image/slide 1.png"
            class="d-block w-100"
            alt="jual action figure"
          />
        </div>
        <div class="carousel-item" data-bs-interval="2000">
          <img
            src="/image/slide 2.png"
            class="d-block w-100"
            alt="jual gundam model kit"
          />
        </div>
        <div class="carousel-item">
          <img
            src="/image/slide 3.png"
            class="d-block w-100"
            alt="jual nendoroid"
          />
        </div>
        <div class="carousel-item">
          <img
            src="/image/slide 4.png"
            class="d-block w-100"
            alt="jual replika senjata"
          />
        </div>
      </div>
      <button
        class="carousel-control-prev"
        type="button"
        data-bs-target="#carouselExampleInterval"
        data-bs-slide="prev"
      >
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button
        class="carousel-control-next"
        type="button"
        data-bs-target="#carouselExampleInterval"
        data-bs-slide="next"
      >
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
  </section>
  <!-- end carousel header -->

  <!-- video profile -->
  <div class="container videoProfile">
    <center>
      <h1 class="title">video profile</h1>

      <iframe
        src="https://www.youtube.com/embed/9mX1rdTIbRs"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
        class="mt-2 mb-4"
      ></iframe>
    </center>
  </div>
  <!-- end video profile -->

  <!-- card produk -->
  <section id="listProduk">
    <div class="container">
      <div class="row">
        <div
          class="col-sm-12 col-md-6 col-lg-6 col-xl-3 d-flex justify-content-center mb-3"
        >
          <a to="#"><img src="/image/figure.jpg" alt="action figure" /></a>
        </div>
        <div
          class="col-sm-12 col-md-6 col-lg-6 col-xl-3 d-flex justify-content-center mb-3"
        >
          <a to="#"><img src="/image/nendoroid.jpg" alt="nendoroid" /></a>
        </div>
        <div
          class="col-sm-12 col-md-6 col-lg-6 col-xl-3 d-flex justify-content-center mb-3"
        >
          <a to="#"><img src="/image/model kit.jpg" alt="model kit" /></a>
        </div>
        <div
          class="col-sm-12 col-md-6 col-lg-6 col-xl-3 d-flex justify-content-center mb-3"
        >
          <a to="#"><img src="/image/replika.jpg" alt="weapon replika" /></a>
        </div>
      </div>
    </div>
  </section>
  <!-- end card produk -->

  <!-- rekomendasi -->
  <section id="Recommendations" class="mt-3">
    <center>
      <h1 class="title fw-bold">Our Recommendations</h1>
    </center>
    <div class="container mt-4">
      <div class="row">
        <div
          class="figure col-sm-12 col-md-6 col-lg-6 col-xl-3 d-flex justify-content-center mb-3"
          v-for="p in products
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
      <center>
        <NuxtLink to="/products"
          ><button
            type="button"
            class="btn btn-outline-primary btn-showAll mb-3"
          >
            Show All
          </button></NuxtLink
        >
      </center>
    </div>
  </section>
  <!-- end rekomendasi -->

  <!-- jastip -->
  <section id="jastip" class="mt-5">
    <center>
      <h1 class="title fw-bold">
        Action Figure yang oni-chan cari enggak ada?
      </h1>
      <p class="descTitle mt-3 fw-medium">
        Kami menyediakan jasa titip / request action figure impor dari jepang
        agar husbando/waifu/loli/catalyst mu bisa pulang ke pelukan mu
      </p>
    </center>
    <div class="container d-flex justify-content-center mt-2">
      <div class="jastip">
        <div class="mb-3">
          <label for="exampleFormControlInput1" class="form-label"
            >Email Kamu</label
          >
          <input
            type="email"
            class="form-control"
            id="exampleFormControlInput1"
            placeholder="Masukan email aktif mu agar bisa kami hubungi..."
            required
          />
        </div>
        <div class="mb-3">
          <label for="exampleFormControlInput1" class="form-label"
            >Nama Karakter / barang</label
          >
          <input
            type="email"
            class="form-control"
            id="exampleFormControlInput1"
            placeholder="Nama husbando/waifu/loli/catalyst yang ingin oni-chan request..."
            required
          />
        </div>
        <div class="mb-3">
          <label for="exampleFormControlInput1" class="form-label">Anime</label>
          <input
            type="email"
            class="form-control"
            id="exampleFormControlInput1"
            placeholder="Ketikan nama anime husbando/waifu/loli/catalyst yang oni-chan request..."
            required
          />
        </div>
        <div class="mb-3">
          <label for="exampleFormControlInput1" class="form-label"
            >Jenis barang</label
          >
          <select class="form-select" aria-label="Default select example">
            <option selected>Jenis barang yang di request</option>
            <option value="action figure">Action Figure</option>
            <option value="Nendoroid">Nendoroid</option>
            <option value="Model Kit">Gundam Model Kit</option>
            <option value="Weapon Replika">Weapon Replika</option>
          </select>
        </div>
        <div class="mb-3">
          <label for="formFile" class="form-label">Foto barang</label>
          <input class="form-control" type="file" id="formFile" required />
          <div id="imageHelp" class="file-text fw-light mt-2">
            Bisa sertakan gambar husbando/waifu/loli yang oni-chan request
            <br />
            agar kami lebih mudah dalam mencarinya...
          </div>
        </div>
        <div class="buttonJast d-flex justify-content-end">
          <button
            type="button"
            class="btn btn-outline-primary btn-jastip mb-3"
            data-bs-toggle="modal"
            data-bs-target="#exampleModal"
          >
            Kirim
          </button>
        </div>
      </div>
    </div>
  </section>
  <!-- end jastip -->

  <!-- google maps -->
  <div class="container maps">
    <center>
      <h1 class="title mt-4">
        Oni-chan pengen liat action figure secara langsung?
      </h1>
      <p class="descTitle">
        Oni-chan bisa mengunjungi toko kami secara langsung, lokasi kami bisa
        dilihat di maps yang ada di bawah ini.
      </p>
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d15810.575997353662!2d110.3970178!3d-7.8274513!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xaad77b93e39dc1d2!2sAnigame!5e0!3m2!1sid!2sid!4v1666768849626!5m2!1sid!2sid"
        style="border: 0"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        class="mb-4"
      ></iframe>
    </center>
  </div>
  <!-- end google maps -->
</template>

<script setup>
// fetch data from json file
const { data: products } = await useFetch(
  "https://my-json-server.typicode.com/raflyhmk/json-figuartz/products"
);

console.log(products.value);
</script>

<style></style>
