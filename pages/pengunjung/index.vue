<template>
    <div class="intro" style="background-color:#6278B1">
        <div class="text-center">
            <h2>Riwayat kunjungan</h2>
            <div class="row m-0">
                <div class="col-sm-1">
                    <div class="icon1">
                        <svg xmlns="http://www.w3.org/2000/svg" width="150" height="40" fill="currentColor" class="bi bi-chevron-left" viewBox="0 0 16 16">
                            <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0"/>
                        </svg>
                    </div>
                </div>
                <div class="col-sm-9">
                    <input type="text" style="box-shadow: 2px 2px 2px #424242;" class="form-control" placeholder="Cari..." aria-label="Cari ..." />
                </div>
                <div class="my-3" style="font-size: medium;">Menampilkan 4 dari 4</div>
                <table class="table">
                    <thead>
                        <tr>
                            <td>#</td>
                            <td>NAMA</td>
                            <td>KATEGORI</td>
                            <td>KELAS</td>
                            <td>WAKTU</td>
                            <td>KEPERLUAN</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <th>1.</th>
                            <td>Fani Karina</td>
                            <td>Siswa</td>
                            <td>XI PPLG 3</td>
                            <td>10 Maret 2024, 29.57.00</td>
                            <td>Membaca buku</td>
                        </tr>
                        <tr>
                            <th>2.</th>
                            <td>Fani lagi</td>
                            <td>Siswa</td>
                            <td>XI PPLG 3</td>
                            <td>10 Maret 2024, 29.57.00</td>
                            <td>Membaca buku</td>
                        </tr>
                        <tr>
                            <th>3.</th>
                            <td>Fani lagi</td>
                            <td>Siswa</td>
                            <td>XI PPLG 3</td>
                            <td>10 Maret 2024, 29.57.00</td>
                            <td>Membaca buku</td>
                        </tr>
                        <tr>
                            <th>4.</th>
                            <td>Fani lagi</td>
                            <td>Siswa</td>
                            <td>XI PPLG 3</td>
                            <td>10 Maret 2024, 29.57.00</td>
                            <td>Membaca buku</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<style scoped>
.text-center{
    padding-top: 5%;
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
    color: white;
    text-align: center;
}
.form-control{
    width: 115%;
}
.icon1{
    color: white;
}
.my-3{
    text-align: left;
    padding-top: 5%;
    color: white;
}
.table{
    font-size:medium;
    color: white;
}
</style>