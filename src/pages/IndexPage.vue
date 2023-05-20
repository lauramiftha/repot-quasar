<template>
  <q-page>
    <q-container class="q-pa-md">
      <q-page-sticky position="top">
        <q-header elevated class="bg-primary text-white">
          <q-toolbar>
            <q-toolbar-title class="text-white">
              Selamat Datang di Aplikasi Web Kegiatan Perusahaan!
            </q-toolbar-title>
          </q-toolbar>
        </q-header>
      </q-page-sticky> </q-container
    ><br />
    <br /><br />
    <hr />
    <br />
    <br />
    <br /><br />
    <br /><br />
    <div class="text-center">
      <router-link to="page-info">Go To Info Page</router-link>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});
</script>
