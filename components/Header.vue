<template>
    <div class="row p-3 bg-primary text-white d-flex align-items-center sticky-top" style="width: 100%; left: 0; right: 0;">
        <div class="col-md-1">
            <img src="~/assets/img/logo-smkn4.webp" alt="logo SMKN 4" />     
        </div>
        <div class="col-md text-white spartan" style="">
            <h1 class="fw-bold">PERPUSTAKAAN DIGITAL</h1>
        </div>
    </div>
</template>

<style scoped>
img{
    width: 80px;
}
h1{
    padding-top: 1%;
    font-family: "League Spartan", sans-serif;
}


@media only screen and (max-width: 600px){
    .row{
        text-align: center;
    }
    img{
        width: 50px;
    }
    h1{
        padding-top: 5%
    }
}
@media only screen and (min-width:600px) and (max-width:900px){
    h1{
        margin-left: 5%;
    }
    
}
</style>