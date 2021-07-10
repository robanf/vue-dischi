<template>
  <div class="my-main">
      <div class="container">
          <div class="row">
              <div class="col">
                    <select name="generi" id="generi" v-model="franco" :onchange="filtro()">
                        <option value="All">All</option>
                        <option value="Rock">Rock</option>
                        <option value="Pop">Pop</option>
                        <option value="Jazz">Jazz</option>
                        <option value="Metal">Metal</option>
                    </select>
                </div>
          </div>
          <div class="row g-3">
              <div v-for="(song,index) in songlist" :key="index" class="col-3 my-song" >
                  <img :src="song.poster" alt="">
                  <div class="fs-5 fw-bolder">{{song.title}}</div>
                  <div class="my-text">{{song.author}}</div>
                  <div class="my-text">{{song.year}}</div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
    name:'Mainsong',
    data(){
        return{
            apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
            songlist:[],
            franco:"All",
            filtrato:"",
        }
    },
    created(){
        this.getSong();
    },
    computed:{
        filtersong(){
            return this.songlist.filter( item =>{
                return console.log(item.genre.includes(this.filtrato));
            })
        },
        Test(){
            return console.log(this.franco);
        }
    },
    methods:{
        getSong(){
            axios
                .get(this.apiUrl)
                .then(response =>{
                    //console.log(response.data.response);
                    this.songlist = response.data.response;
                    console.log(this.songlist);
                })
        },
        filtro(){

            if(this.franco=="All"){
                this.filtrato="";
            }
            else{
                this.filtrato=this.franco;
            }
            console.log(this.filtrato)
        }
    }
}
</script>

<style lang="scss" scoped>
.my-main{
    background-color: #1e2d3b;

        .my-song{
            background-color: #2e3a46;
            text-align: center;
            margin: 20px 20px;
            height: 300px;
            width: calc(100% / 5 - 40px);
            color: white;
            img{
                margin: 15px 0px;
                height: 50%;
            }
            .my-text{
                color: #777471;
            }
        }
}
</style>

