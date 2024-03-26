<template>
   <div class="container-fluid pb-5">
        <div class="text-center text-white pt-5">
            <h2>Isi kunjungan</h2>
        </div>
        <div class="layer mt-5">
            <form class="py-3">
                <div class="row m-3 d-flex justify-content-center">
                    <div class="col-sm-12">
                        <input type="text" style="box-shadow: 2px 2px 2px #424242;" class="form-control" placeholder="Nama ..." aria-label="Nama ..." />
                    </div>
                </div>
                <div class="row m-3 justify-content-center">
                    <div class="col-sm-12">
                        <select class="form-control form-control-lg form-select" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="">Kategori ...</option>
                            <option>Siswa</option>
                            <option>Guru</option>
                            <option>Staf</option>
                            <option>Umum</option>
                        </select>
                    </div>
                </div>
                <div class="row m-3 justify-content-center">
                    <div class="col-sm-4 mb-2">
                        <select class="form-select" aria-label="Disabled select example" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="">Tingkatan</option>
                            <option value="X">X</option>
                            <option value="XI">XI</option>
                            <option value="XII">XII</option>
                        </select>
                    </div>
                    <div class="col-sm-4 justify-content-center mb-2">
                        <select class="form-select" aria-label="Disabled select example" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="">Jurusan</option>
                            <option value="TJKT">TJKT</option>
                            <option value="TBSM">TBSM</option>
                            <option value="PPLG">PPLG</option>
                            <option value="DKV">DKV</option>
                            <option value="TOI">TOI</option>
                        </select>
                    </div>
                    <div class="col-sm-4 justify-content-center mb-2">
                        <select class="form-select" aria-label="Disabled select example" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="">Kelas</option>
                            <option value="1">1</option>
                            <option value="2">2</option>
                            <option value="3">3</option>
                            <option value="4">4</option>
                        </select>
                    </div>
                </div>
                <div class="row m-3 justify-content-center">
                    <div class="col-sm-12">
                        <select class="form-control" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="">Keperluan ...</option>
                            <option>Membaca</option>
                            <option>Meminjam Buku</option>
                            <option>Berkunjung</option>
                            <option>Mengembalikan Buku</option>
                        </select>
                    </div>
                </div>
                <div class="text-center">
                    <NuxtLink to="/pengunjung">
                        <input type="submit" class="btn" value="Kirim">
                    </NuxtLink>
                </div>
            </form>
        </div>
    </div>
</template>

<style scoped>
@media only screen and (min-width:900px){
    .layer{
        margin-left: 0% 20%;
        margin:10%;
    }
}

.text-center{
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
}
.layer{
    background-color: #cbd2e5;
    border-radius: 25px;
    box-shadow: 2px 2px 2px #424242;
}
.btn{
    background-color: white;
    box-shadow: 2px 2px 2px #424242;
    color: black;
}
</style>