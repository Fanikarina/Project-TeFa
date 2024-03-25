<template>
    <div class="container-fluid pb-5" style="background-color:#6278B1">
        <div class="text-center text-white pt-5">
            <h2>Pencarian buku</h2>
        </div>
        <div class="content text-white pt-3 ">
            <div class="row m-0">
                <div class="col-sm-1">
                    <div class="icon1">
                        <svg xmlns="http://www.w3.org/2000/svg" width="150" height="40" fill="currentColor" class="bi bi-chevron-left" viewBox="0 0 16 16">
                            <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0"/>
                        </svg>
                    </div>
                </div>
                <div class="col-sm-2">
                    <select class="form-select" aria-label="Default select example" style="box-shadow: 2px 2px 2px #424242;">
                        <option selected>Novel</option>
                        <option value="1">Pendidikan</option>
                        <option value="2">Novel</option>
                        <option value="3">Komik</option>
                    </select>
                </div>
                <div class="col-sm-7">
                    <input type="text" style="box-shadow: 2px 2px 2px #424242;" class="form-control" placeholder="Mariposa" aria-label="Mariposa" />
                </div>
            </div>
            <div class="my-3" style="font-size: medium;">Menampilkan 1 dari 1</div>
            <div class="layer">
                <div class="row buku">
                    <div class="col-lg-2">
                        <div class="card">
                            <img src="~/assets/img/mariposa.jpeg" class="card-img-top" alt="...">
                            <div class="card-body">
                                <a href="#" class="btn" style="margin-top: -20%;">Lihat detail</a>
                            </div>
                        </div>
                    </div>
                    <div class="layer2">
                        <div class="col-lg-8">
                            <h2 class="text text-center">Detail buku</h2>
                            <div class="sinopsis">
                                <p>Judul : Mariposa 2</p>
                                <p>Penulis : Luluk HF</p> 
                                <p>Penerbit : Coconut Books</p> 
                                <p>Tahun terbit :  5 Februari 2022</p>
                                <p>Sinopsis buku : </p>
                                    <p class="keterangan">Meninggalnya Mr. Bov menciptakan kehancuran bagi Iqbal. Iqbal menyalahkan Acha atas kepergian papanya itu. Melihat kondisi Iqbal yang tak kunjung membaik membuat keluarga besar Iqbal memutuskan untuk pindah ke Prancis. Di tengah permasalahan hubungan Iqbal dan Acha, datanglah Glen yang selalu ada di samping Acha.</p> 
                                <p>Kategori : Novel</p>
                                <p>Rak : 02</p>
                            </div>
                            <NuxtLink to="/buku">
                                <input type="submit" class="button" value="Tutup">
                            </NuxtLink>
                        </div>
                    </div>
                </div>
            </div>
        </div>  
    </div>
</template>

<style scoped>
.text-center{
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
}
.content{
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
    text-align: center;
}
.form-control{
    width: 115%;
}
.my-3{
    padding-right: 75%;
    padding-top: 3%;
    color: white;
}
.layer{
    margin-top: 1%;
    background-color: #cbd2e5;
    border-radius: 25px;
    width: 90%;
    margin-left: 5%;
    box-shadow: 2px 2px 2px #727272;
}
.row.buku{
    padding-top: 2%;
    margin-left: 2%;
    border-radius: 50px;
    
}
.card{
    height: 48%;
    box-shadow: 1px 1px 1px #424242;
}
.card-img-top{
    width: 80%;
    height: 100%;
    object-fit: cover;
    object-position: 0 30;
    padding-top: 5%;
    margin-left: 10%;
}

.layer2{
    background-color: #ffffff;
    border-radius: 25px;
    width: 70%;
    margin-left: 5%;
    margin-bottom: 2%;
    box-shadow: 1px 1px 1px #424242;
}
.text.text-center{
    padding-top: 3%;
    font-family: "League Spartan", sans-serif;
    font-size: 65%;
    color: rgb(0, 0, 0);
    text-align: center;
    margin-left: 50%;

}
.sinopsis{
    font-family: "League Spartan", sans-serif;
    font-size: 50%;
    color: rgb(0, 0, 0);
    text-align: left;
    margin-left: 5%;
}
.keterangan{
    margin-left: 20%;
}
.button{
    font-size: medium;
    background-color: white;
    width: 12%;
    border-radius: 10%;
    box-shadow: 1px 1px 1px #8a8a8a;
    margin-left: 120%;
    margin-bottom: 2%;
}
</style>
        