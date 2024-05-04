<template>
    <div class="container-fluid pb-5" style="background-color:#6278B1">
        <div class="text-center text-white pt-5">
            <h2>Pencarian buku</h2>
        </div>
        <div class="content text-white pt-3 ">
            <div class="row m-0">
                <div class="col-sm-1">
                    <NuxtLink to="/buku/" style="color:white !important">
                        <div class="icon1">
                            <svg xmlns="http://www.w3.org/2000/svg" width="150" height="40" fill="currentColor"
                                class="bi bi-chevron-left" viewBox="0 0 16 16">
                                <path fill-rule="evenodd"
                                    d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0" />
                            </svg>
                        </div>
                    </NuxtLink>
                </div>
                <div class="col-sm-2 mb-2">
                    <select class="form-select" aria-label="Default select example"
                        style="box-shadow: 2px 2px 2px #424242;">
                        <option value="">Kategori buku</option>
                        <option v-for="(kategori, i) in kategories" :key="i" :value="kategori.nama">{{ kategori.nama }}
                        </option>
                    </select>
                </div>
                <div class="col-sm-8">
                    <input type="text" style="box-shadow: 2px 2px 2px #424242;" class="form-control" placeholder=""
                        aria-label="" />
                </div>
            </div>
            <div class="my-3" style="font-size: medium;">Menampilkan {{ buku.length }} dari {{ buku.length }}</div>
            <div class="layer">
                <div class="card">
                    <img :src="buku.cover_buku" class="cover" alt="cover buku">
                </div>
                <div class="layer2">
                    <h2 class="text text-center">Detail buku</h2>
                    <div class="sinopsis">
                        <p>Judul : {{ buku.judul }}</p>
                        <p>Penulis : {{ buku.penulis }}</p>
                        <p>Penerbit : {{ buku.penerbit }}</p>
                        <p>Tahun terbit : {{ buku.tahun_terbit }}</p>
                        <p>Sinopsis : {{ buku.sinopsis }}</p>
                        <p>Kategori : {{ buku.kategori_buku?.nama }}</p>
                        <p>Rak : {{ buku.rak }}</p>
                    </div>
                    <NuxtLink to="/buku/">
                        <input type="submit" class="button" value="Tutup">
                    </NuxtLink>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const supabase = useSupabaseClient()

const route = useRoute()
const buku = ref([])
const kategories = ref([])

const getBookById = async () => {
    const { data, error } = await supabase.from('buku').select(`*,kategori_buku(*)`).eq('id', route.params.id)
    if (data) buku.value = data[0]
    data.forEach(book => {
        const { data } = supabase.storage.from('coverBuku').getPublicUrl(book.cover_buku)
        if (data) {
            book.cover_buku = data.publicUrl
        }
    })
}
const getKategori = async () => {
    const { data, error } = await supabase.from('kategori_buku').select('*')
    if (data) kategories.value = data
}

onMounted(() => {
    getBookById()
    getKategori()
})
</script>


<style scoped>
@media only screen and (max-width:900px) {
    .layer {
        flex-direction: column;
        margin-top: 1%;
        background-color: #cbd2e5;
        border-radius: 25px;
        width: 100%;
        box-shadow: 2px 2px 2px #727272;
    }

    .row.buku {
        padding-top: 2%;
        margin-left: 2%;
        border-radius: 50px;

    }

    .card {
        box-shadow: 1px 1px 1px #424242;
        margin-bottom: 2rem;
        margin: auto;
    }

    .card-img-top {
        object-fit: cover;
        object-position: 0 30;
        /* padding-top: 5%; */
    }

    .layer2 {
        background-color: #ffffff;
        border-radius: 25px;
        width: 100%;
        margin: auto;
        box-shadow: 1px 1px 1px #424242;
    }
}


.text-center {
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
}

.content {
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
    text-align: center;
}

.my-3 {
    padding-right: 75%;
    padding-top: 3%;
    color: white;
}

.layer {
    display: flex;
    justify-content: center;
    align-items: start;
    gap: 45px;
    padding: 46px;
    width: 100%;
    margin-top: 1%;
    background-color: #cbd2e5;
    border-radius: 25px;
    box-shadow: 2px 2px 2px #727272;
}

.row.buku {
    padding-top: 2%;
    margin-left: 2%;
    border-radius: 50px;

}

.card {
    box-shadow: 1px 1px 1px #424242;
    margin-bottom: 2rem;
    padding: 10px;
}

.card-img-top {
    object-fit: cover;
    object-position: 0 30;
    /* padding-top: 5%; */
    margin: auto;
}

.layer2 {
    background-color: #ffffff;
    border-radius: 25px;
    width: 100%;
    margin-bottom: 2%;
    box-shadow: 1px 1px 1px #424242;
}

.text.text-center {
    padding-top: 3%;
    font-family: "League Spartan", sans-serif;
    font-size: 65%;
    color: rgb(0, 0, 0);
    text-align: center;

}

.sinopsis {
    font-family: "League Spartan", sans-serif;
    font-size: 50%;
    color: rgb(0, 0, 0);
    text-align: left;
    margin-left: 5%;
}

.keterangan {
    margin: auto;
}

.button {
    font-size: medium;
    background-color: white;
    border-radius: 10%;
    box-shadow: 1px 1px 1px #8a8a8a;
    margin-bottom: 2%;
}
</style>
