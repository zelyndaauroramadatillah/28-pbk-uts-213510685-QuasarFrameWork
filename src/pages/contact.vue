<template>
    <q-page>
      <q-container class="q-py-lg">
        <q-card class="q-mb-md">
          <q-card-section class="q-pt-none">
            <q-item>
              <q-item-section avatar>
                <q-icon name="location_on" color="primary" size="2rem" />
              </q-item-section>

              <q-item-section>
                <q-item-label>
                  Jl. Kaharuddin Nasution 113<br />
                  Pekanbaru 28284 Riau -<br />
                  Indonesia
                </q-item-label>
              </q-item-section>
            </q-item>

            <q-item>
              <q-item-section avatar>
                <q-icon name="phone" color="primary" size="2rem" />
              </q-item-section>

              <q-item-section>
                <q-item-label>
                  +62831-8527-5855
                </q-item-label>
              </q-item-section>
            </q-item>

            <q-item>
              <q-item-section avatar>
                <q-icon name="mail" color="primary" size="2rem" />
              </q-item-section>

              <q-item-section>
                <q-item-label>
                  info@example.com
                </q-item-label>
              </q-item-section>
            </q-item>

            <q-item>
              <q-item-section avatar>
                <q-icon name="schedule" color="primary" size="2rem" />
              </q-item-section>

              <q-item-section>
                <q-item-label>
                  Senin - Jumat<br />
                  08:00 - 17:00 WIB
                </q-item-label>
              </q-item-section>
            </q-item>
          </q-card-section>
        </q-card>

        <q-card class="q-py-md">
          <q-card-section class="q-py-none">
            <q-item>
              <q-item-section>
                <q-item-label header>
                  Hubungi Kami
                </q-item-label>
              </q-item-section>
            </q-item>

            <q-item>
              <q-item-section>
                <q-input
                  filled
                  type="text"
                  v-model="name"
                  label="Nama Lengkap"
                  outlined
                />
              </q-item-section>
            </q-item>

            <q-item>
              <q-item-section>
                <q-input
                  filled
                  type="email"
                  v-model="email"
                  label="Email"
                  outlined
                />
              </q-item-section>
            </q-item>

            <q-item>
              <q-item-section>
                <q-input
                  filled
                  type="tel"
                  v-model="phone"
                  label="Nomor Telepon"
                  outlined
                />
              </q-item-section>
            </q-item>

            <q-item>
              <q-item-section>
                <q-textarea
                  filled
                  v-model="message"
                  label="Pesan"
                  outlined
                />
              </q-item-section>
            </q-item>

            <q-item>
              <q-item-section>
                <q-btn
                  color="primary"
                  label="Kirim"
                  @click="submitForm"
                />
              </q-item-section>
            </q-item>
          </q-card-section>
        </q-card>
      </q-container>
    </q-page>
  </template>
<script>
export default {
  name: 'ContactPage',
  data () {
    return {
      name: '',
      email: '',
      phone: '',
      message: ''
    }
  },
  methods: {
    submitForm () {
      const subject = `Pesan dari ${this.name} (${this.email})`
      const body = `
        Nama: ${this.name}\r\n
        Email: ${this.email}\r\n
        Telepon: ${this.phone}\r\n
        Pesan: ${this.message}\r\n
      `
      window.location.href = `mailto:contoh@alamat-email.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`
    }
  }
}
</script>
