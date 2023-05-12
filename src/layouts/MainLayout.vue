<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
        <q-toolbar-title>
          <div>
            Input Kegiatan Karyawan Apps
          </div>
        </q-toolbar-title>
        <q-space />
        <q-btn
          icon="info"
          round
          dense
          @click="showAbout = true"
        />
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="drawer">
      <q-list>
        <q-item
          v-for="route in routes"
          :key="route.path"
          :to="route.path"
          clickable
        >
          <q-item-label>
            {{ route.name }}
          </q-item-label>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer elevated class="bg-dark text-white">
      <div class="text-center">
        &copy; {{ new Date().getFullYear() }} Zelynda Aurora  Mardatillah
      </div>
    </q-footer>

    <q-dialog
      v-model="showAbout"
      title="About My App"
      no-cancel-btn
    >
      <q-card>
        <q-card-section class="text-center">
          <q-img
            src="https://i.pinimg.com/originals/54/d0/77/54d077e99876c05b2301c9577c6e6477.gif"
            style="max-width: 200px;"
            class="q-mb-md"
          />
          <p>
            Worker Activity Apps is a simple application that allows users to manage their tasks and schedule their activities more effectively.
          </p>
          <p>
            Developed by Zelynda Aurora Mardatillah.
          </p>
        </q-card-section>
        <q-card-actions align="right">
          <q-btn
            label="Close"
            color="secondary"
            @click="showAbout = false"
          />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </q-layout>
</template>
<script>

export default {
  name: 'MainLayout',
  data () {
    return {
      drawer: false,
      showAbout: false,
      routes: [
        {
          path: '/',
          name: 'Home'
        },
        {
          path: '/about',
          name: 'About'
        },
        {
          path: '/Contact',
          name: 'Contact'
        }
      ]
    }
  },
  methods: {
    toggleLeftDrawer () {
      this.drawer = !this.drawer
    }
  }
}
</script>

<style>
.q-toolbar-title {
  font-size: 24px;
  font-weight: bold;
  text-align: center;
  flex-grow: 1;
}

.q-header {
  background-color: #3f51b5;
  color: #fff;
}

.q-drawer {
  background-color: #f5f5f5;
}

.q-list {
  padding: 16px;
}

.q-footer {
  padding: 16px;
}

.q-dialog {
  max-width: 400px;
}

.q-card {
  background-color: #fff;
  padding: 16px;
  border-radius: 4px;
}

.q-card-actions {
  padding-top: 16px;
  text-align: right;
}

.q-btn {
  text-transform: uppercase;
  font-weight: bold;
}

.q-btn-secondary {
  color: #3f51b5;
}

</style>
