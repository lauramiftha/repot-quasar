<!-- eslint-disable vue/multi-word-component-names -->
// eslint-disable-next-line vue/multi-word-component-names
<template>
  <div>
    <q-page-container>
      <q-header>
        <q-toolbar color="primary">
          <q-toolbar-title class="text-white">
            Selamat Datang di Aplikasi Web Kegiatan Perusahaan!
          </q-toolbar-title>
        </q-toolbar>
      </q-header>
      <q-page>
        <q-card class="q-ma-md">
          <q-card-section>
            <h6>
              Temukan kegiatan menarik yang diadakan oleh perusahaan kami.
            </h6>
          </q-card-section>
          <q-card-section>
            <q-btn
              @click="tampilkanKegiatan"
              label="Tampilkan Kegiatan"
              color="primary"
            />
          </q-card-section>
          <q-card-section v-if="kegiatanDitampilkan">
            <h2>Daftar Kegiatan Perusahaan</h2>
            <transition-group name="fade" tag="ul" class="q-my-md">
              <li v-for="kegiatan in daftarKegiatan" :key="kegiatan.id">
                {{ kegiatan.nama }}
              </li>
            </transition-group>
            <form @submit.prevent="tambahKegiatan" class="q-mt-md">
              <q-input
                filled
                label="Nama Kegiatan"
                v-model="namaKegiatan"
                required
                class="q-mb-md"
              />
              <q-btn type="submit" label="Tambah Kegiatan" color="primary" />
            </form>
          </q-card-section>
        </q-card>
      </q-page>
    </q-page-container>
  </div>
</template>

<script>
export default {
  // Komponen aplikasi web kegiatan perusahaan
  name: "AplikasiKegiatanPerusahaan",
  data() {
    return {
      kegiatanDitampilkan: false,
      daftarKegiatan: [], // Daftar kegiatan perusahaan
      namaKegiatan: "", // Nama kegiatan yang akan ditambahkan
    };
  },
  methods: {
    tampilkanKegiatan() {
      this.kegiatanDitampilkan = true;
    },
    tambahKegiatan() {
      if (this.namaKegiatan) {
        const kegiatanBaru = {
          id: this.daftarKegiatan.length + 1,
          nama: this.namaKegiatan,
        };
        this.daftarKegiatan.push(kegiatanBaru);
        this.namaKegiatan = ""; // Reset input nama kegiatan setelah ditambahkan
      }
    },
  },
};
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
