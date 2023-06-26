<template>
  <div class="kategori">
    <!-- eslint-disable -->
    <li class = "card" style="width: 18rem;" v-for="data in jenis">
      <p>{{data.kode}}</p>
      <p>{{data.jenis_kategori}}</p>
      <button>Baca</button>
    </li>
  </div>
</template>

<script>
import axios from "axios";
import {ref} from "vue";

const dataKategori='http://localhost/bookstore/selectallkategori.php';

export default {
  data(){
    return{
      jenis:ref([]),
    }
  },
  mounted() {
    this.DataKategori();
  },
  methods: {
    DataKategori(){
      axios.get(dataKategori).then((resp) => {
        console.log(resp);
        this.jenis=resp.data
      })
          .catch((err)=>{
            console.log(err);
          })
    }

  }
}
</script>

<style scoped>
.kategori{
  display: flex;
  flex-wrap: wrap;
  alignment: center;
  padding-left: 20px;
}
p{
  color: black;
}
.card{
  text-align: center;
  margin-left: 50px;
  margin-bottom: 20px;
  padding-top: 20px;
}
</style>