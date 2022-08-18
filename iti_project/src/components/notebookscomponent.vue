<template>
                <div class="d-flex flex-row flex-wrap justify-content-between ">
                    <div  class="card my-3" style="width:20rem">
                        <img src="" class="card-img-top product-img" alt="" id="productimg">
                        <div class="card-body" v-for="notebook in notebook" :key="notebook.price">
                            <p class="card-text text-center">{{notebook.image}} </p>
                            <h5 class="card-title text-center">{{notebook.name}} </h5>
                            <p class="card-text text-center">{{notebook.details}} </p>
                            <h6 class="card-title ">{{notebook.price}} $</h6>
                            <div class="d-flex justify-content-center align-items-baseline">
                                <button class="btn btn-success px-5" @click="addProductToCart">Add to cart <i class="fa-solid fa-cart-shopping"></i></button>
                            </div>
                        </div>
                    </div>
                </div>

</template>
<script>
//  import students from '../students'

import notebookscomponent from './notebookscomponent.vue'


export default {
    async created(){
      const res= await fetch("http://localhost:3000/notebook");
      this.notebook=await res.json();
    },
    data(){
        return{
        notebook : [],
        }
    },components:{
    notebookscomponent,
},
    methods: {
     
    }
}


</script>