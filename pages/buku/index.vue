<template>
  <div class="container-fluid pb-5" style="background-color: #6278b1">
    <div class="text-center text-white pt-5">
      <h2>Pencarian buku</h2>
    </div>
    <div class="layer pt-3 justify-content-center text-white">
      <div class="row m-0">
        <div class="layer2 pt-2">
          <div class="row">
            <div class="col-sm-1">
              <NuxtLink to="/" style="color: white !important">
                <div class="icon1">
                  <i class="bi bi-chevron-left"></i>
                </div>
              </NuxtLink>
            </div>
            <div class="col-sm-3 mb-2">
              <select v-model="keyword" class="form-select" aria-label="Default select example" style="box-shadow: 2px 2px 2px #424242">
                <option value="">Kategori buku</option>
                <option v-for="(kategori, i) in kategories" :key="i" :value="kategori.nama">{{ kategori.nama }}</option>
              </select>
            </div>
            <form @submit.prevent="getBooks" class="col mb-3">
              <div class="input-group flex-nowrap rounded" style="box-shadow: 2px 2px 2px #424242">
                <input v-model="keyword" type="search" class="form-control" placeholder="Cari..." aria-label="Search" />
                <span class="input-group-text">
                  <i class="bi bi-search"></i>
                </span>
              </div>
            </form>
          </div>
        </div>
      </div>
      <div class="tampil">
        <div class="pt-1 ms-4 text-white" style="font-size: medium">Menampilkan {{ bookFiltered.length }} dari {{ jumlahbk }} buku</div>
      </div>
      <div class="layer3 p-4">
        <div class="row buku">
          <div v-for="(book, i) in bookFiltered" :key="i" class="col mb-3">
            <div class="card rounded-4">
              <img :src="book.cover_buku" class="card-img-top rounded mx-auto" alt="..." />
              <NuxtLink :to="`/buku/${book.id}`" style="text-decoration: none">
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
<script setup>
const supabase = useSupabaseClient();

const kategories = ref([]);
const keyword = ref("");
const books = ref([]);
const jumlahbk = ref(0);

const getBooks = async () => {
  const { data, error } = await supabase.from("buku").select(`*,kategori(*)`).ilike("judul", `%${keyword.value}%`);
  if (data) {
    books.value = data;
    data.forEach((book) => {
      const { data } = supabase.storage.from("coverBuku").getPublicUrl(book.cover_buku);
      if (data) {
        book.cover_buku = data.publicUrl;
      }
    });
  }
};

const getKategori = async () => {
  const { data, error } = await supabase.from("kategori_buku").select("*");
  if (data) kategories.value = data;
};

const bookFiltered = computed(() => {
  return books.value.filter((b) => {
    return b.judul?.toLowerCase().includes(keyword.value?.toLowerCase()) || b.kategori?.nama.toLowerCase().includes(keyword.value?.toLowerCase());
  });
});

const getJumlahbk = async () => {
  const { data, count } = await supabase.from("buku").select("*", { count: "exact" });
  if (data) jumlahbk.value = count;
};

onMounted(() => {
  getBooks();
  getKategori();
  getJumlahbk();
});
</script>
<style scoped>
.tampil{
  text-shadow: 1px 1px 5px rgb(51, 49, 49);
}
.text-center {
  font-family: "League Spartan", sans-serif;
  font-size: 190%;
}
.container-fluid {
  font-family: "League Spartan", sans-serif;
  font-size: 190%;
}
.input-group-text {
  background-color: #fff;
  border-left: none !important;
}
.form-control {
  border-right: none;
}
.layer2 {
  width: 80%;
  margin: auto;
  padding: 0;
}
.layer3 {
  background-color: #cbd2e5;
  border-radius: 25px;
  margin: auto;
  box-shadow: 2px 2px 2px #424242;
}
.buku {
  border-radius: 50px;
  object-fit: cover;
}
.card {
  height: 200px;
  width: 140px;
  margin: auto;
}
.card-img-top {
  width: 75%;
  object-fit: cover;
  object-position: 0 30;
  padding-top: 5%;
  margin: auto;
}
.btn {
  font-size: 50%;
}
</style>
