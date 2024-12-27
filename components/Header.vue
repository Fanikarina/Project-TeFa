<template>
    <div class="row p-3 bg-primary text-white d-flex align-items-center">
        <div class="col-md-1">
            <img src="~/assets/img/logo-smkn4.png" alt="logo SMKN 4" />     
        </div>
        <div class="col-md ps-5 text-white spartan" style="">
            <h1>PERPUSTAKAAN DIGITAL</h1>
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@700&display=swap');
img{
    width: 120px;
}

@media only screen and (max-width: 600px){
    .row{
        text-align: center;
    }
    img{
        width: 60px;
    }
    h1{
        font-size: large;
        padding-top: 5%
    }
}
@media only screen and (min-width:600px) and (max-width:900px){
    h1{
        margin-left: 5%;
    }
    
}
</style>