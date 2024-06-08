<template>
    <div class="container-fluid pb-5" style="background-color:#6278B1">
        <div class="row text-center p-5 text-white">
            <h2 class="fw-bold">Riwayat kunjungan</h2>
        </div>
        <div class="row m-0 text-white">
            <div class="layer pt2">
                <div class="row">
                    <div class="col-lg-1 col-md-2 col-sm-3 col-3 p-0">
                        <div class="icon1">
                            <NuxtLink to="/" style="color:white !important">
                                <svg xmlns="http://www.w3.org/2000/svg" width="90" height="40" fill="currentColor" class="bi bi-chevron-left" viewBox="0 0 16 16">
                                    <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0"/>
                                </svg>
                            </NuxtLink>
                        </div>
                    </div>
                    <form @submit.prevent="getPengunjung" class="col-lg-11 col-md-9 col-sm-8 col-9">
                        <div class="input-group rounded" style="box-shadow: 2px 2px 2px #424242">
                            <input v-model="keyword" type="search" class="form-control" placeholder="Cari berdasarkan nama dan kategori..." aria-label="Search" />
                            <span class="input-group-text">
                                <i class="bi bi-search"></i>
                            </span>
                        </div>
                    </form>  
                </div>
            </div>
        </div>
        <div class="tampil">
            <div class="my-3 text-white pt-4" style="font-size: medium;">Menampilkan {{ visitors.length }} dari {{ jmlpengunjung }} </div>
        </div>
        <div class="table-responsive">
            <table class="table table-bordered text-white text-center " style="font-size: medium;">
                <thead>
                    <tr>
                        <td>No</td>
                        <td>NAMA</td>
                        <td>KATEGORI</td>
                        <td>KELAS</td>
                        <td>WAKTU</td>
                        <td>KEPERLUAN</td>
                    </tr>
                </thead> 
                <tbody>
                    <tr v-for="(visitor,i) in pengunjungFiltered" :key="i" >
                        <th>{{ i+1 }}</th>
                        <td>{{ visitor.nama }}</td>
                        <td>{{ visitor.keanggotaan.nama }}</td>
                        <td>{{ visitor.tingkat }} {{ visitor.jurusan }} {{ visitor.kelas }}</td>
                        <td>{{ visitor.tanggal }}, {{ visitor.waktu.split('.')[0] }}</td>
                        <td>{{ visitor.keperluan.nama }}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>
<script setup>
const supabase= useSupabaseClient()

const visitors = ref([])
const keyword = ref('')
const jmlpengunjung= ref(0) 

const getPengunjung = async () => {
    const { data, error } = await supabase.from('pengunjung')
    .select(`*,keanggotaan(*),keperluan(*)`)
    .order('id', {ascending : false})
    .ilike("nama", `%${keyword.value}%`)
    if (data) visitors.value = data
}

const getJmlpengunjung = async () =>{
    const{ data, count } = await supabase
    .from("pengunjung") 
    .select('*', { count: "exact" })
    if(data) jmlpengunjung.value = count
}

const pengunjungFiltered = computed (() =>{
    return visitors.value.filter((b) =>{
        return (
            b.nama?.toLowerCase().includes(keyword.value?.toLowerCase()) || 
            b.keanggotaan?.nama.toLowerCase().includes(keyword.value?.toLowerCase())
        )
    })
})

onMounted(() => {
    getPengunjung()
    getJmlpengunjung()
})
</script>

<style scoped>
/* .container-fluid{
} */

.text-center{
    font-family: "League Spartan", sans-serif;
    font-size: 100%;
}
.input-group-text {
    background-color: #fff;
    border-left: none !important;
}
.layer{
    width: 90%;
    margin-left: 5%;
    padding: 0;
}
.tampil{
    margin-left: 8%;
}

.table-responsive{
    max-height: 208px;
    padding: 0;
    /* width: 85%; */
    margin: 0px 25px;
    
}
.table{
    /* margin: ; */
    padding: 0;

}
.form-control {
    border-right:none;
}

thead {
    background-color: #3b4b77bb;
    position: sticky;
    top: 0;
}
</style>