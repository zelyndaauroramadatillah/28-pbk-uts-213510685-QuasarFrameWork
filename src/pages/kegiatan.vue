<template>
    <div id="container">
      <h1>Register Kegiatan Zelynda Aurora Mardhatillah</h1>
      <!-- Form -->
      <form @submit.prevent="tambahKegiatan">
        <div>
          <label for="nama">Nama Kegiatan</label>
          <input type="text" id="nama" v-model="kegiatan.nama" />
        </div>
        <div>
          <label for="deskripsi">Deskripsi Kegiatan</label>
          <textarea id="deskripsi" v-model="kegiatan.deskripsi"></textarea>
        </div>
        <button type="submit">Tambahkan</button>
        <button type="button" @click="resetInput">Reset</button>
        <button type="button" @click="batalTambah" v-if="kegiatan.nama || kegiatan.deskripsi">Batal</button>
      </form>
      <!-- Filter -->
      <div>
        <label for="filter">Tampilkan Kegiatan Belum Selesai</label>
        <input type="checkbox" id="filter" v-model="filterDone" @change="filterKegiatan" />
      </div>
      <!-- Kegiatan List -->
      <ul>
        <li v-for="(kegiatan, index) in kegiatanList" :key="index" :class="{ done: kegiatan.done, hidden: filterDone && kegiatan.done }">
          <h3>{{ kegiatan.nama }}</h3>
          <p>{{ kegiatan.deskripsi }}</p>
          <button @click="hapusKegiatan(index)">Delete</button>
          <button @click="toggleDone(index)">
            {{ kegiatan.done ? 'Belum Selesai' : 'Sudah Selesai' }}
          </button>
        </li>
      </ul>
      <!-- Footer -->
      <div class="footer-wrapper">
        <div class="footer">
          <p>&copy; 2023 Zelynda Aurora Mardhatillah</p>
          <a href="mailto:zelyndaauroramardatillah@student.uir.ac.id">Gmail</a>
          <a href="https://instagram.com/zelyndaaurora_?igshid=YmMyMTA2M2Y=">Instagram</a>
        </div>
      </div>
      <router-view></router-view>
    </div>
  </template>
<script>
export default {
  name: 'KegiatanPage',
  _components: {},
  get components () {
    return this._components
  },
  set components (value) {
    this._components = value
  },
  data () {
    return {
      kegiatan: {
        nama: '',
        deskripsi: '',
        done: false
      },
      kegiatanList: [],
      filterDone: false
    }
  },
  methods: {
    tambahKegiatan () {
      this.kegiatanList.push(this.kegiatan)
      this.kegiatan = {
        nama: '',
        deskripsi: '',
        done: false
      }
    },
    resetInput () {
      this.kegiatan = {
        nama: '',
        deskripsi: '',
        done: false
      }
    },
    batalTambah () {
      this.kegiatan = {
        nama: '',
        deskripsi: '',
        done: false
      }
    },
    hapusKegiatan (index) {
      this.kegiatanList.splice(index, 1)
    },
    toggleDone (index) {
      this.kegiatanList[index].done = !this.kegiatanList[index].done
    },
    filterKegiatan () {
      if (this.filterDone) {
        this.kegiatanList = this.kegiatanList.filter(kegiatan => !kegiatan.done)
      } else {
        this.kegiatanList = JSON.parse(localStorage.getItem('kegiatanList')) || []
      }
    }
  },
  mounted () {
    this.kegiatanList = JSON.parse(localStorage.getItem('kegiatanList')) || []
  },
  watch: {
    kegiatanList: function (newList) {
      localStorage.setItem('kegiatanList', JSON.stringify(newList))
    }
  }
}
</script>
<style>
  .done {
    text-decoration: line-through;
  }
  .hidden {
    display: none;
  }

  body {
  background-image: url('https://wallpapercave.com/wp/wp4737516.jpg');
  background-size: cover;
  background-repeat: no-repeat;
}

  h1 {
  font-size: 3rem;
  text-align: center;
  margin-bottom: 2rem;
}

form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
}

form input[type="text"],
form button[type="submit"] {
  width: 100%;
  max-width: 20rem;
  margin: 0.5rem 0;
}

form label {
  display: block;
  text-align: center;
  margin-bottom: 0.5rem;
}

input[type="text"],
textarea {
  padding: 0.5rem;
  font-size: 1.2rem;
  border-radius: 0.3rem;
  border: 0.5px solid #ccc;
}

button {
  padding: 0.8rem 1rem;
  font-size: 1.2rem;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 0.3rem;
  cursor: pointer;
  margin-right: 1rem;
}

button:hover {
  background-color: #3e8e41;
}

button.cancel {
  background-color: #ff9800;
}

button.cancel:hover {
  background-color: #f57c00;
}

button.delete {
  background-color: #f44336;
}

button.delete:hover {
  background-color: #d32f2f;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

li {
  border: 1px solid #ccc;
  border-radius: 0.3rem;
  padding: 1rem;
  margin-bottom: 1rem;
  transition: all 0.3s ease-in-out;
  position: relative;
}

li:hover {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  border-color: #4CAF50;
}

li button {
  position: absolute;
  top: 0;
  right: 0;
  padding: 0.4rem 2rem;
  font-size: 1rem;
  background-color: transparent;
  color: #555;
  border: none;
  cursor: pointer;
}

li button:hover {
  color: #000000;
}

li button:first-child {
  right: 5rem;
}

li button:last-child {
  right: 5rem;
}

li h3 {
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}

li p {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

.done {
  text-decoration: line-through;
  opacity: 0.5;
}

.hidden {
  display: none;
}

.footer {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #6b6868;
    padding: 10px;
  }
  .footer a {
    margin-left: 10px;
    color: #ffffff;
    text-decoration: none;
  }
</style>
