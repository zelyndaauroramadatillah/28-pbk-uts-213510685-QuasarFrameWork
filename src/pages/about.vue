<template>
    <q-page class="about">
      <q-page-container>
        <div class="about-content">
          <h1 class="about-title">Tentang Aplikasi</h1>
          <h2 class="about-subtitle">Profil Aplikasi</h2>
          <p class="about-text">
            Aplikasi Input Kegiatan adalah sebuah aplikasi sederhana yang memungkinkan pengguna untuk mencatat kegiatan-kegiatan yang sudah dilakukan atau akan dilakukan dalam waktu dekat. Dengan menggunakan aplikasi ini, pengguna dapat mengatur jadwal dan rencana kegiatan dengan lebih mudah dan efisien.
          </p>
          <h2 class="about-subtitle">Profil Developer</h2>
          <div class="developer-profile">
            <q-img
              src="../assets/2.jpg"
              alt="Zelynda Aurora Mardhatillah"
              class="developer-image"
              contain
              style="max-width: 150px;"
            />
            <p class="about-text">
              Aplikasi Input Kegiatan dikembangkan oleh Zelynda Aurora Mardhatillah, seorang mahasiswi di Universitas Islam Riau. Zelynda memiliki minat yang besar dalam bidang teknologi dan selalu mencoba untuk mengembangkan keterampilannya dalam pengembangan aplikasi web. Zelynda berharap aplikasi ini dapat membantu banyak orang dalam mengatur kegiatan-kegiatan mereka dengan lebih mudah dan efisien.
            </p>
          </div>
        </div>
      </q-page-container>
    </q-page>
  </template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AboutPage'
})
</script>

  <style scoped>
  .about {
    max-width: 800px;
    margin: 0 auto;
    padding: 50px 20px;
  }

  .about-title {
    font-size: 36px;
    font-weight: bold;
    text-align: center;
    margin-bottom: 30px;
  }

  .about-subtitle {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 15px;
  }

  .about-text {
    font-size: 18px;
    line-height: 1.5;
    text-align: justify;
  }

  .developer-profile q-img {
  margin-right: 20px;
  display: inline-block;
  border-radius: 50%;
}

</style>
