Persiapan Penggunaan Vue.js dan Axios
Untuk memulai penggunaan framework Vue.js, Anda dapat melakukannya dengan menggunakan npm atau secara manual. Dalam praktikum kali ini, kita akan menggunakan metode manual. Yang Anda perlukan adalah library Vue.js dan Axios untuk melakukan panggilan API REST, menggunakan CDN.

Library Vue.js
Anda dapat menyertakan Vue.js dalam proyek Anda dengan menambahkan baris berikut di dalam tag <head> atau sebelum tag penutup </body> di file HTML Anda:

<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
Library Axios
Sertakan Axios dalam proyek Anda dengan menambahkan baris berikut di dalam tag <head> atau sebelum tag penutup </body> di file HTML Anda:

<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
Struktur Direktori Proyek
Untuk memulai proyek dengan basis web sederhana, Anda dapat mengatur struktur direktori seperti berikut:

.<br>
├── index.html<br>
└── assets<br>
    ├── css<br>
    │   └── style.css<br>
    └── js<br>
        └── app.js
Dalam struktur direktori ini, Anda memiliki:

index.html: File utama HTML dari proyek Anda. <br>
assets: Direktori untuk menyimpan semua aset proyek. <br>
css: Direktori untuk file-file stylesheet. <br>
style.css: File stylesheet utama proyek. <br>
js: Direktori untuk file-file JavaScript. <br>
app.js: File JavaScript utama dari proyek Anda. <br>

# Menampikan Data 
File = index.html <br>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Frontend Vuejs</title>
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
    <link rel="stylesheet" href="assets/css/style.css">
</head>
<body>
    <div id="app">
        <h1>Daftar Artikel</h1>
        <button id="btn-tambah" @click="tambah">Tambah Data</button>
        <div class="modal" v-if="showForm">
            <div class="modal-content">
                <span class="close" @click="showForm = false">&times;</span>
                <form id="form-data" @submit.prevent="saveData">
                    <h3 id="form-title">{{ formTitle }}</h3>
                    <div><input type="text" name="judul" id="judul" v-model="formData.judul" placeholder="Judul" required></div>
                    <div><textarea name="isi" id="isi" rows="10" v-model="formData.isi"></textarea></div>
                    <div>
                        <select name="status" id="status" v-model="formData.status">
                            <option v-for="option in statusOptions" :value="option.value">
                                {{ option.text }}
                            </option>
                        </select>
                    </div>
                    <input type="hidden" id="id" v-model="formData.id">
                    <button type="submit" id="btnSimpan">Simpan</button>
                    <button @click="showForm = false">Batal</button>
                </form>
            </div>
        </div>
        <table>
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Judul</th>
                    <th>Status</th>
                    <th>Aksi</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(row, index) in artikel">
                    <td class="center-text">{{ row.id }}</td>
                    <td>{{ row.judul }}</td>
                    <td>{{ statusText(row.status) }}</td>
                    <td class="center-text">
                        <a href="#" @click="edit(row)">Edit</a>
                        <a href="#" @click="hapus(index, row.id)">Hapus</a>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
    <script src="assets/js/app.js"></script>
</body>
</html>

