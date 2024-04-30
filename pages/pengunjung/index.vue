<template>
    <div class="container-fluid pb-5" style="background-color:#6278B1">
        <div class="text-center p-5 text-white">
            <h2>Riwayat kunjungan</h2>
        </div>
        <div class="row m-0 text-white">
            <div class="layer pt2">
                <div class="row">
                    <div class="col-lg-1 col-4">
                        <div class="icon1">
                            <NuxtLink to="/">
                                <svg xmlns="http://www.w3.org/2000/svg" width="150" height="40" fill="currentColor" class="bi bi-chevron-left" viewBox="0 0 16 16">
                                    <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0"/>
                                </svg>
                            </NuxtLink>
                        </div>
                    </div>
                    <div class="col-sm-10 col-7 mb-2">
                        <div class="input-group flex-nowrap rounded" style="box-shadow: 2px 2px 2px #424242;">
                            <input type="search" class="form-control" placeholder="Cari..." aria-label="Search" />
                            <span class="input-group-text">
                                <i class="bi bi-search"></i>
                            </span> 
                        </div>
                    </div>   
                </div>
            </div>
        </div>
        <div class="my-3 ps-2 text-white pt-5"  style="font-size: medium;">Menampilkan 4 dari 4</div>
        <div class="table-responsive">
            <table class="table table-bordered text-white text-center " style="font-size: medium;">
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
</template>

<style scoped>

.text-center{
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
}
.input-group-text {
    background-color: #fff;
    border-left: none !important;
}
.layer{
    width: 90%;
    margin-left: 5%;
    padding: 0;
}
.table{
    padding: 0;
}
.form-control {
    border-right:none;
}
</style>