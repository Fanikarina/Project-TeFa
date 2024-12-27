<template>
   <div class="container-fluid pb-5">
        <div class="text-center text-white pt-5">
            <h2>Isi kunjungan</h2>
        </div>
        <div class="layer mt-5" >
            <form @submit.prevent="kirimData" class="py-3" autocomplete="off">
                <div class="row m-3 d-flex justify-content-center">
                    <div class="col-sm-12">
                        <input v-model.trim="nama" type="text" style="box-shadow: 2px 2px 2px #424242;" class="form-control" placeholder="Nama" aria-label="Nama" required/>
                    </div>
                </div>
                <div class="row m-3 justify-content-center">
                    <div class="col-sm-12">
                        <select @change="cekKeanggotaan" v-model="keanggotaan" class="form-control form-control-lg form-select" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="" disabled>Kategori</option>
                            <option v-for="(keanggotaan,i) in members" :key="i" :value="keanggotaan.id">{{ keanggotaan.nama }}</option>
                        </select>
                    </div>
                </div>
                <div class="row m-3 justify-content-center" v-if="keanggotaan == '2'"> 
                    <div class="col-sm-4 mb-2">
                        <select v-model="tingkat" class="form-select" aria-label="Disabled select example" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="" disabled>Tingkatan</option>
                            <option value="X">X</option>
                            <option value="XI">XI</option>
                            <option value="XII">XII</option>
                        </select>
                    </div>
                    <div class="col-sm-4 justify-content-center mb-2">
                        <select v-model="jurusan" class="form-select" aria-label="Disabled select example" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="" disabled>Jurusan</option>
                            <option value="TJKT">TJKT</option>
                            <option value="TBSM">TBSM</option>
                            <option value="PPLG">PPLG</option>
                            <option value="DKV">DKV</option>
                            <option value="TOI">TOI</option>
                        </select>
                    </div>
                    <div class="col-sm-4 justify-content-center mb-2">
                        <select v-model="kelas" class="form-select" aria-label="Disabled select example" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="" disabled>Kelas</option>
                            <option value="1">1</option>
                            <option value="2">2</option>
                            <option value="3">3</option>
                            <option value="4">4</option>
                        </select>
                    </div>
                </div>
                <div class="row m-3 justify-content-center">
                    <div class="col-sm-12">
                        <select v-model="keperluan" class="form-control" style="box-shadow: 2px 2px 2px #424242;">
                            <option value="" disabled>Keperluan</option>
                            <option v-for="(item,i) in objectives" :key="i" :value="item.id">{{ item.nama }}</option>
                        </select>
                    </div>
                </div>
                <div class="text-center">
                    <input type="submit" class="btn" value="Kirim">
                </div>
            </form>
        </div>
    </div>
</template>
<script setup>
const supabase= useSupabaseClient()

const members = ref([])
const objectives = ref([])
const nama = ref("");
const keanggotaan = ref("");
const keperluan = ref("");
const tingkat = ref("");
const jurusan = ref("");
const kelas = ref("");

const kirimData = async () => {
    const { error } = await supabase.from('pengunjung')
    .insert([{
        nama:nama.value,
        keanggotaan:keanggotaan.value,
        keperluan:keperluan.value,
        tingkat:tingkat.value,
        jurusan:jurusan.value,
        kelas:kelas.value
    }])
    console.log(error)
    if (error) throw error
    else navigateTo('/pengunjung/')
}
const getKeanggotaan = async () =>{
    const { data, error } = await supabase.from('keanggotaan').select('*')
    if (data) members.value = data
}
const getKeperluan = async () =>{
    const { data, error } = await supabase.from('keperluan').select('*')
    if (data) objectives.value = data
}
const cekKeanggotaan = e => {
    if(e.target.value != '2'){
        tingkat.value=""
        jurusan.value=""
        kelas.value=""  
    }

}
onMounted(() =>{
    getKeanggotaan()
    getKeperluan()
})

</script>

<style scoped>
@media only screen and (min-width:900px){
    .layer{
        margin-left: 0% 20%;
        margin:10%;
    }
}
.text-center{
    font-family: "League Spartan", sans-serif;
    font-size: 190%;
}
.layer{
    background-color: #cbd2e5;
    border-radius: 25px;
    box-shadow: 2px 2px 2px #424242;
}
.btn{
    background-color: white;
    box-shadow: 2px 2px 2px #424242;
    color: black;
}
</style>