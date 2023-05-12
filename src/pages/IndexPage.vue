<template>
  <body>
    <div class="home">
      <div class="hero-section">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-title">Aplikasi Input Kegiatan Karyawan</h1>
            <p class="hero-description">Catat kegiatanmu dengan mudah dan cepat</p>
            <router-link to="/kegiatan">
              <button class="hero-button">Mulai Input Kegiatan</button>
            </router-link>
          </div>
          <div class="hero-image">
            <img src="https://www.bluwave.id/storage/app/media/AboutUs/contact.png" alt="hero image">
          </div>
        </div>
      </div>
    </div>
  </body>
</template>

<script>
export default {
  name: 'HomePage'
}
</script>

<style>
.home {
  font-family: sans-serif;
  background-image: url('https://wallpapercave.com/wp/wp1836757.jpg');
  background-size: cover;
  background-position: center center;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-section {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.hero-content {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.hero-text {
  max-width: 600px;
  margin-right: 20px;
  text-align: center;
}

.hero-title {
  font-size: 48px;
  margin-bottom: 20px;
  color: #333;
}

.hero-description {
  font-size: 24px;
  margin-bottom: 40px;
  color: #ffffff;
}
.hero-button {
    background-color: #609966;
    color: #fff;
    border: none;
    padding: 12px 24px;
    border-radius: 6px;
    font-size: 18px;
    cursor: pointer;
}
.hero-button:hover {
  background-color: #0056b3;
}

.hero-image {
  max-width: 600px;
}

.hero-image img {
  max-width: 100%;
  height: auto;
}
</style>
