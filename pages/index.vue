<template>
    <div class="container-fluid">
        <div class="text-center">
            <h1>SELAMAT DATANG . . .</h1>
        </div>
        <div class="row my-5 justify-content-center">
            <div class="col-lg-4" >
                <nuxt-link to="/pengunjung/tambah">
                    <div class="card bg-pengunjung rounded-5 mb-4">
                        <div class="card-body text-dark mt-5">
                            <h2>Kunjungan</h2> 
                        </div>
                    </div> 
                </nuxt-link> 
            </div>
            <div class="col-lg-4" >
                <nuxt-link to="buku">
                    <div class="card bg-buku rounded-5">
                        <div class="card-body text-dark mt-5">
                            <h2>Cari buku</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
        <div class="row pb-5 justify-content-center">
            <div class="col-lg-4">
                <nuxt-link to="/pengunjung">
                    <div class="card bg-riwayat rounded-5 mb-4">
                        <div class="card-body text-dark mt-5">
                            <h2>3 Pengunjung</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
            <div class="col-lg-4">
                <nuxt-link to="/buku">
                    <div class="card buku rounded-5">
                        <div class="card-body text-dark mt-5">
                            <h2>2 Buku</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@700&display=swap');
.container-fluid{
    background-color: #6278B1;
}
h1{
    padding-top: 5%;
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
    color: white;
    text-align: center;
}
/* .text-center{
    color: black;
    text-align: center;
    margin-top: -27%;
} */
/* .transparan {
    background-color: rgba(255, 255, 255, 0.652);
    border-radius: 30px;
    box-shadow: 1px 1px 10px #424242;
} */
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
    background-image: url('../assets/img/kunjungan.png');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
    /* opacity:0.2 ; */
}

.card.bg-buku{
    background: url('../assets/img/cariBuku.png') no-repeat center center;
    background-size: cover;
    /* opacity: 0.2; */
}
.card.bg-riwayat{
    background: url('../assets/img/riwayat.png') no-repeat center center;
    background-size: cover;
    /* opacity: 0.3;    */
}
.card.buku{
    background: url('../assets//img/bukuu.png') no-repeat center center;
    background-size: cover;
    /* opacity: 0.3;    */
}

</style>