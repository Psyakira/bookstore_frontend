<template>
  <div class="listanggota">
    <li class = "card" style="width: 18rem;" v-for="data in anggota">
      <p>{{data.nama}}</p>
      <p>{{data.jenis_kelamin}}</p>
      <p>{{data.alamat}}</p>
    </li>
  </div>
</template>

<script>
import axios from "axios";
import {ref} from "vue";

const dataAnggota='http://localhost/bookstore/selectallanggota.php';

export default {
  data(){
    return{
      anggota:ref([]),

    }
  },
  mounted() {
    this.DataAnggota();
  },
  methods: {
    DataAnggota(){
      axios.get(dataAnggota).then((resp) => {
        console.log(resp);
        this.anggota=resp.data
      })
          .catch((err)=>{
            console.log(err);
          })
    }

  }
}
</script>

<style scoped>
.listanggota{
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