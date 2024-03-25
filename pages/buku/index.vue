<template>
    <div class="container-fluid pb-5" style="background-color:#6278B1">
        <div class="text-center text-white pt-5">
            <h2>Pencarian buku</h2>
        </div>
        <div class="layer pt-3 justify-content-center text-white">
            <div class="row m-0">
                <div class="layer2 pt-2">
                    <div class="row">
                        <div class="col-sm-1 ">
                            <div class="icon1">
                                <i class="bi bi-chevron-left"></i>
                            </div>
                        </div>
                        <div class="col-sm-3 mb-2">
                            <select class="form-select" aria-label="Default select example" style="box-shadow: 2px 2px 2px #424242;">
                                <option selected>Kategori buku</option>
                                <option value="1">Pendidikan</option>
                                <option value="2">Novel</option>
                                <option value="3">Komik</option>
                            </select>
                        </div>
                        <div class="col-sm-8 mb-2">
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
            <div class="pt-5 ps-5 ms-4 text-white" style="font-size: medium;">Menampilkan 2 dari 2</div>
            <div class="layer3 p-4">
                <div class="row buku">
                    <div class="col-lg-2 mb-4">
                        <div class="card">
                            <img src="~/assets/img/bot.jpeg" class="card-img-top" alt="...">
                            <div class="card-body p-0">
                                <a href="#" class="btn d-flex justify-content-center">Lihat detail</a>
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2 mb-4">
                        <div class="card">
                            <img src="~/assets/img/mariposa.jpeg" class="card-img-top" alt="...">
                            <NuxtLink to="/detail">
                                <div class="card-body p-0">
                                    <a href="#" class="btn d-flex justify-content-center">Lihat detail</a>
                                </div>
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
.container-fluid{
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
}
.input-group-text {
  background-color: #fff;
  border-left: none !important;
}
.form-control {
  border-right:none;
}
.layer2{
    width: 90%;
    margin-left: 5%;
    padding: 0;
}
.layer3{
    background-color: #cbd2e5;
    border-radius: 25px;
    width: 90%;
    margin-left: 5%;
    box-shadow: 2px 2px 2px #424242;
}
.row.buku{
    border-radius: 50px;
    object-fit: cover;
    
}

.card-img-top{
    width: 80%;
    height: 100%;
    object-fit: cover;
    object-position: 0 30;
    padding-top: 5%;
    margin-left: 10%;
}
.btn{
    font-size: 50%;
}
</style>
        