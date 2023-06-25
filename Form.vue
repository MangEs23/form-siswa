<template>
    <div class="col">
        <div>
            <h1 class="mb-4">Daftar Nilai Siswa</h1>
            <form ref="form" @submit.prevent="handleSubmit">
                <div class="form-group mt-2">
                    <label for="nis">NIS:</label>
                    <input id="nis" class="form-control" type="number" v-model="nis" required>
                </div>

                <div class="form-group mt-2">
                    <label for="nama">Nama:</label>
                    <input id="nama" class="form-control" type="text" v-model="nama" required>
                </div>

                <div class="form-group mt-2">
                    <label for="input1">Nilai 1:</label>
                    <input id="input1" class="form-control" type="number" v-model.number="nilai1" required>
                </div>

                <div class="form-group mt-2">
                    <label for="input2">Nilai 2:</label>
                    <input id="input2" class="form-control" type="number" v-model.number="nilai2" required>
                </div>

                <div class="form-group mt-2">
                    <label for="input3">Nilai 3:</label>
                    <input id="input3" class="form-control" type="number" v-model.number="nilai3" required>
                </div>

                <div class="form-group mt-3">
                    <button type="submit" class="btn btn-primary">Submit</button>
                </div>
            </form>

            <!-- <div v-if="rataRata !== null" class="mt-4">
                <h2>Rata-Rata: {{ rataRata }}</h2>
            </div> -->
        </div>
    </div>
</template>
  
<script>
export default {
    data() {
        return {
            nis: '',
            nama: '',
            nilai1: null,
            nilai2: null,
            nilai3: null,
            rataRata: null
        };
    },
    methods: {
        handleSubmit() {
            const sum = this.nilai1 + this.nilai2 + this.nilai3;
            this.rataRata = sum / 3;
            this.$emit('submit-siswa', {
                nis: this.nis,
                nama: this.nama,
                nilai1: this.nilai1,
                nilai2: this.nilai2,
                nilai3: this.nilai3,
                rataRata: this.rataRata.toFixed(2)
            });
            if (this.rataRata != null) {
                alert(`Rata-Rata: ${this.rataRata.toFixed(2)}`);
            }
            this.resetForm();
        },
        resetForm() {
            this.nis = '';
            this.nama = '';
            this.nilai1 = null;
            this.nilai2 = null;
            this.nilai3 = null;
        }
    }
};
</script>
  