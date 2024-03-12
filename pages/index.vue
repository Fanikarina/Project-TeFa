<template>
    <div class="intro" style="background-color:#6278B1">
        <div >
            <h1>SELAMAT DATANG . . .</h1>
        </div>
        <div class="container-fluid">
            <div class="row my-5">
                <div class="col-lg-4" style="margin-left: 17%;">
                    <div class="transparan">
                        <nuxt-link to="/pengunjung/tambah">
                            <div class="card bg-pengunjung rounded-5">
                                <div class="card-body"> 
                                </div>
                            </div> 
                        </nuxt-link> 
                    </div>
                    <div class="text-center">
                        <h2>Kunjungan</h2>
                    </div>
                </div>
                <div class="col-lg-4" style="margin-right: 10%;">
                    <div class="transparan">
                        <nuxt-link to="buku">
                            <div class="card bg-buku rounded-5">
                                <div class="card-body">
                                </div>
                            </div>
                        </nuxt-link>
                    </div> 
                    <div class="text-center">
                        <h2>Cari buku</h2>
                    </div>   
                </div>
            </div>
            <div class="row my-5" style="padding-top: 5%;">
                <div class="col-lg-4" style="margin-left: 17%;">
                    <div class="transparan">
                        <nuxt-link to="/pengunjung">
                            <div class="card bg-riwayat rounded-5">
                                <div class="card-body">
                                </div>
                            </div>
                        </nuxt-link>
                    </div> 
                    <div class="text-center">
                        <h2>4 Pengunjung</h2>
                    </div> 
                </div>
                <div class="col-lg-4">
                    <div class="transparan">
                        <nuxt-link to="/buku">
                            <div class="card buku rounded-5">
                                <div class="card-body">
                                </div>
                            </div>
                        </nuxt-link>
                    </div> 
                    <div class="text-center">
                        <h2>2 Buku</h2>
                    </div> 
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@700&display=swap');
.intro{
    height: 650px;
}
h1{
    padding-top: 5%;
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
    color: white;
    text-align: center;
}
.text-center{
    color: black;
    text-align: center;
margin-top: -27%;
}
.transparan {
    background-color: rgba(255, 255, 255, 0.652);
    border-radius: 30px;
    box-shadow: 1px 1px 10px #424242;
}
.bg{
    height: 200px;
    box-shadow: 1px 1px 10px #424242;
}
.card{
    align-items: center;
    height: 200px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung{
    background-image: url('../assets/img/kunjugan.jpg');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
    opacity:0.2 ;
}

.card.bg-buku{
    background: url('../assets/img/buku.jpg') no-repeat center center;
    background-size: cover;
    opacity: 0.2;
}
.card.bg-riwayat{
    background: url('../assets/img/riwayat.jpeg') no-repeat center center;
    background-size: cover;
    opacity: 0.3;   
}
.card.buku{
    background: url('../assets/img/buku-bg.jpg') no-repeat center center;
    background-size: cover;
    opacity: 0.3;   
}

</style>