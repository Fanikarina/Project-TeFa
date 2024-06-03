<template>
    <div class="container-fluid">
        <div class="text-center">
            <h2>SELAMAT DATANG . . .</h2>
        </div>
        <div class="row my-4 justify-content-center">
            <div class="col-lg-4 col-6" >
                <nuxt-link to="/pengunjung/tambah" style="text-decoration:none">
                    <div class="card bg-pengunjung rounded-5 mb-4">
                        <div class="card-body text-dark mt-5">
                            <h3>Kunjungan</h3> 
                        </div>
                    </div> 
                </nuxt-link> 
            </div>
            <div class="col-lg-4 col-6" >
                <nuxt-link to="buku" style="text-decoration:none">
                    <div class="card bg-buku rounded-5 ">
                        <div class="card-body text-dark mt-5">
                            <h3>Cari buku</h3>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
        <div class="row pb-5 justify-content-center">
            <form @submit.prevent="getPengunjung" class="col-lg-4 col-6">
                <nuxt-link to="/pengunjung" style="text-decoration:none">
                    <div class="card bg-riwayat rounded-5 mb-4">
                        <div class="card-body text-dark mt-5">
                            <h3>{{ visitors?.length }} Pengunjung</h3>
                        </div>
                    </div>
                </nuxt-link>
            </form>
            <form @submit.prevent="getBooks" class="col-lg-4 col-6">
                <nuxt-link to="/buku" style="text-decoration:none">
                    <div class="card buku rounded-5">
                        <div class="card-body text-dark mt-5">
                            <h3>{{ books?.length }} Buku</h3>
                        </div>
                    </div>
                </nuxt-link>
            </form>
        </div>
    </div>
</template>
<script setup>
const supabase = useSupabaseClient();

const books = ref([])
const visitors = ref([])
const keyword = ref('')


const getBooks = async () => {
  const { data, error } = await supabase.from("buku").select(`*,kategori(*)`).ilike("judul", `%${keyword.value}`)
  if (data) {
    books.value = data;
  }
};

const getPengunjung = async () => {
    const { data, error } = await supabase.from('pengunjung')
    .select(`*,keanggotaan(*),keperluan(*)`).ilike("nama", `%${keyword.value}`)
    if (data) visitors.value = data
}

onMounted(()=>{
    getBooks()
    getPengunjung()
})
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@700&display=swap');
@media screen and (max-width:600px) {
    .card{
        height: 40px;
    }
    h2{
        font-size: larger;
        margin-top: 5%;
    }
    h3{
        font-size: large;
        padding-top: 12%;
    }
}
.container-fluid{
    background-color: #6278B1;
}
h2{
    padding-top: 2%;
    font-family: "League Spartan", sans-serif;
    color: white;
    text-align: center;
}

.card{
    align-items: center;
    height: 180px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung{
    background-image: url('../assets/img/kunjungan.png');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
}

.card.bg-buku{
    background: url('../assets/img/cariBuku.png') no-repeat center center;
    background-size: cover;
}
.card.bg-riwayat{
    background: url('../assets/img/riwayat.png') no-repeat center center;
    background-size: cover;
}
.card.buku{
    background: url('../assets//img/bukuu.png') no-repeat center center;
    background-size: cover;
}

</style>