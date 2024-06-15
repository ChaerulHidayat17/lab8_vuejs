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
