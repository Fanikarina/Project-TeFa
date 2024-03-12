<template>
    <div class="intro" style="background-color:#6278B1">
        <div class="text-center">
            <h2>Pencarian buku</h2>
        </div>
        <div class="container-fluid">
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
                        <option selected>Kategori buku</option>
                        <option value="1">Pendidikan</option>
                        <option value="2">Novel</option>
                        <option value="3">Komik</option>
                    </select>
                </div>
                <div class="col-sm-7">
                    <input type="text" style="box-shadow: 2px 2px 2px #424242;" class="form-control" placeholder="Mau cari buku apa..." aria-label="Mau cari buku apa ..." />
                </div>
            </div>
            <div class="my-3" style="font-size: medium;">Menampilkan 2 dari 2</div>
            <div class="layer">
                <div class="row buku">
                    <div class="col-lg-2">
                        <div class="card">
                            <img src="~/assets/img/bot.jpeg" class="card-img-top" alt="...">
                            <div class="card-body">
                                <a href="#" class="btn" style="margin-top: -15%;">Lihat detail</a>
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2">
                        <div class="card">
                            <img src="~/assets/img/mariposa.jpeg" class="card-img-top" alt="...">
                            <NuxtLink to="/detail">
                                <div class="card-body">
                                    <a href="#" class="btn" style="margin-top: -20%;">Lihat detail</a>
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
.intro{
    padding: 0;
    height: 550%;
}
.text-center{
    padding-top: 5%;
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
    color: white;
    text-align: center;
}
.container-fluid{
    padding-top: 3%;
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
    color: white;
    text-align: center;
}
.form-control{
    width: 115%;
}
.my-3{
    padding-right: 75%;
    padding-top: 5%;
    color: white;
}
.layer{
    margin-top: 1%;
    background-color: #cbd2e5;
    border-radius: 25px;
    width: 90%;
    margin-left: 5%;
    box-shadow: 2px 2px 2px #424242;
}
.row.buku{
    padding-top: 2%;
    margin-left: 2%;
    border-radius: 50px;
    
}
.card{
    height: 90%;
    width: 100%;
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
        