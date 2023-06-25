<template>
  <div class="container">
    <div class="row">
      <Form @submit-siswa="handleSubmit" />
      <Daftar :daftarNilai="daftarNilai" @delete="deleteItem" />
    </div>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Form from './Form.vue';
import Daftar from './Daftar.vue';
export default {
  components: {
    Form,
    Daftar
  },
  data() {
    return {
      daftarNilai: [],
    };
  },
  methods: {
    handleSubmit(data) {
      console.log(typeof data);
      this.daftarNilai.push(data);
    },
    deleteItem(index) {
      this.daftarNilai.splice(index, 1)
    }
  }
};
</script>
