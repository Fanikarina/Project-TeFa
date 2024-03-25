<template>
    <div class="container-fluid pb-5" style="background-color:#6278B1">
        <div class="text-center p-5 text-white">
            <h2>Riwayat kunjungan</h2>
        </div>
            <div class="row m-0 text-white">
                <div class="layer pt2">
                    <div class="row">
                        <div class="col-sm-1 sp-5">
                            <div class="icon1">
                                <i class="bi bi-chevron-left"></i>
                            </div>
                        </div>
                        <div class="col-sm-11 mb-2">
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
            <table class="table table-bordered text-white text-center" style="font-size: medium;">
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
.form-control {
  border-right:none;
}
</style>