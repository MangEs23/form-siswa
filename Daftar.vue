<template>
  <div class="col mt-5">
    <div class="container mt-5">
      <table class="table table-striped">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">NIS</th>
            <th scope="col">Nama</th>
            <th scope="col">Nilai 1</th>
            <th scope="col">Nilai 2</th>
            <th scope="col">Nilai 3</th>
            <th scope="col">Rata-Rata</th>
            <th scope="col">Aksi</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(daftar, index) in daftarNilai" :key="index" :daftar="daftar" :index="index">
            <th scope="row">{{ index + 1 }}</th>
            <td>{{ daftar.nis }}</td>
            <td>{{ daftar.nama }}</td>
            <td>{{ daftar.nilai1 }}</td>
            <td>{{ daftar.nilai2 }}</td>
            <td>{{ daftar.nilai3 }}</td>
            <td>{{ daftar.rataRata }}</td>
            <td><a href="#" class="btn btn-outline-danger" @click="deleteItem(index)">Delete</a></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    daftarNilai: Array
  },
  methods: {
    deleteItem(index) {
      this.$emit('delete', index);
    }
  }
};
</script>
