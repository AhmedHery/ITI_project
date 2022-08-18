<template>
                <div class="d-flex flex-row flex-wrap justify-content-between ">
                    <div  class="card my-3" style="width:20rem">
                        <img src="" class="card-img-top product-img" alt="" id="productimg">
                        <div class="card-body" v-for="smartphone in smartphones" :key="smartphones.price">
                            <p class="card-text text-center">{{smartphone.image}} </p>
                            <h5 class="card-title text-center">{{smartphone.name}} </h5>
                            <p class="card-text text-center">{{smartphone.details}} </p>
                            <h6 class="card-title ">{{smartphone.price}} $</h6>
                            <div class="d-flex justify-content-center align-items-baseline">
                                <button class="btn btn-success px-5" @click="addProductToCart">Add to cart <i class="fa-solid fa-cart-shopping"></i></button>
                            </div>
                        </div>
                    </div>
                </div>

</template>
<script>
//  import students from '../students'

import smartphonescomponent from './smartphonescomponent.vue'


export default {
    async created(){
      const res= await fetch("http://localhost:3000/smartphones");
      this.smartphones=await res.json();
    },
    data(){
        return{
        smartphones : [],
        }
    },components:{
    smartphonescomponent,
},
    methods: {
     
    }
}


</script>