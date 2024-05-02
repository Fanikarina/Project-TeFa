<script setup>
const supabase = useSupabaseClient()
const route = useRaute()
const buku = ref([])
const getBookById = async () =>{
    const { data, error } = await supabase.from('buku')
    .select(`*,kategori(*)`)
    .eq('id', route.params.id)
    if(data) buku.value = data[0]
}
onMounted(() =>{
    getBookById
})
</script>