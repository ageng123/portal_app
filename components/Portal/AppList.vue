<template>
  <div>
    <b-container fluid class="p-3">
      <b-card
        border-variant="dark"
        header-bg-variant="dark"
        header-text-variant="white"
        header-tag="header"
        footer-tag="footer"
        body-class="pb-0"
        class="mb-3"
      >
        <template v-slot:header>
          <h6 class="mb-0">
            <span class="align-middle">
              <b-icon icon="table" font-scale="2" />
              List Aplikasi
            </span>
          </h6>
        </template>
        <b-row>
          <b-col cols="md-2 sm-12 mb-3">
            <b-btn block variant="success" @click="cardClick()">
              <h1><b-icon icon="people-fill" /></h1>
              Human Resource Information System
            </b-btn>
          </b-col>
          <b-col cols="md-2 sm-12 mb-3">
            <b-btn block variant="success">
              <h1><b-icon icon="table" /></h1>
              Rekap Administrasi Cuti / Izin
            </b-btn>
          </b-col>
        </b-row>
      </b-card>
      <b-card
        border-variant="danger"
        header-bg-variant="danger"
        header-text-variant="white"
        header-tag="header"
        footer-tag="footer"
        class="mb-3"
        body-class="pb-0"
      >
        <template v-slot:header>
          <h6 class="mb-0">
            <b-icon icon="gear-fill" font-scale="2" />
            Master Data Manajemen
          </h6>
        </template>
        <b-row>
          <b-col cols="md-2 sm-12 mb-3">
            <b-btn block variant="danger">
              <h1><b-icon icon="people" /></h1>
              Master Data karyawan
            </b-btn>
          </b-col>
          <b-col cols="md-2 sm-12 mb-3">
            <b-btn block variant="danger">
              <h1><b-icon icon="table" /></h1>
              Master Data Konsumen
            </b-btn>
          </b-col>
        </b-row>
      </b-card>
      <b-card
        border-variant="dark"
        header-bg-variant="dark"
        header-text-variant="white"
        header-tag="header"
        footer-tag="footer"
        class="mb-3"
        header-class="navy navy-border"
        body-class="pb-0"
      >
        <template v-slot:header>
          <h6 class="mb-0">
            <b-icon icon="gear-fill" font-scale="2" />
            Administration Tools
          </h6>
        </template>
        <b-row>
          <b-col cols="md-2 sm-12 mb-3">
            <b-btn block variant="dark" class="navy">
              <h1>
                <b-icon icon="people" />
              </h1>
              Kontrol User Aplikasi
            </b-btn>
          </b-col>
          <b-col cols="md-2 sm-12 mb-3">
            <b-btn block variant="dark" class="navy">
              <h1><b-icon icon="table" /></h1>
              Kontrol Tipe Izin
            </b-btn>
          </b-col>
          <b-col cols="md-2 sm-12 mb-3">
            <b-btn v-b-modal.ModalKontrolAplikasi @click="linkOpener('http://localhost:88/gislayout1')" block variant="dark" class="navy">
              <h1><b-icon icon="table" /></h1>
              Kontrol List Aplikasi
            </b-btn>
          </b-col>
        </b-row>
      </b-card>
    </b-container>
    <KontrolAplikasi />
  </div>
</template>

<script>
import KontrolAplikasi from '~/components/Modal/KontrolAplikasi.vue'
export default {
  name: 'AppList',
  methods: {
    cardClick: () => {
      window.open('https://www.google.com')
    },
    linkOpener: (uri) => {
      window.open(uri)
    }
  },
  components: {
    KontrolAplikasi
  }
}
</script>

<style>
.pointer {
  cursor: pointer;
}
.btn-round {
  border-radius: 50%;
}
.container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.title {
    font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
        'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
}

.subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
}

.links {
    padding-top: 15px;
}
</style>
