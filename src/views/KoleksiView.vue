<template>
  <div class="collection">
  <li class = "card" style="width: 18rem;" v-for="data in buku">
    <p>{{data.judul}}</p>
    <p>by : {{data.pengarang}}</p>
    <p>{{data.penerbit}}</p>
    <p>Rp.{{data.harga}}</p>
  </li>
  </div>
</template>

<script>
import axios from "axios";
import {ref} from "vue";

const dataKoleksi='http://localhost/bookstore/selectallbuku.php';

export default {
  data(){
    return{
      buku:ref([]),

    }
  },
  mounted() {
    this.DataBuku();
  },
  methods: {
    DataBuku(){
      axios.get(dataKoleksi).then((resp) => {
          console.log(resp);
          this.buku=resp.data
          })
          .catch((err)=>{
            console.log(err);
          })
    }

  }
}
</script>

<style scoped>
.collection{
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