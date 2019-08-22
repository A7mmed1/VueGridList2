<template>
  <div class="product-list">
      <div class="view">
          <a href="#" @click="changeView('list')">List</a> | <a href="#" @click="changeView('grid')">Grid</a>
          <hr/>
      </div>


      <div class="products" :class="{ 'grid' : gridView }">


            <product
             v-for="product in products"
             :name="product.name"
             :price="product.price"
             :key="product.id"

             >
                {{product.name}} || {{product.price}}

            </product>
     </div>
  </div>
</template>

<script>
import Product from './Product.vue'
export default {
        components: {
       Product
   },
        methods:{
            changeView(type){
                if(type == 'grid'){
                    this.gridView = true;
                }else {
                    this.gridView = false;
                }
            }

        },
        data(){
            return {
                gridView:false,

            products:[
                    {id:1 , name :'something', price:8.99},
                    {id:2 , name :'something', price:7.99},
                    {id:3 , name :'something', price:9.98},
                    {id:4 , name :'something', price:9.98}




            ]
        }
    }


}
</script>
<style lang="scss">

    .product-list{
        padding: 2rem;
        border: solid #ccc;
        border-radius: 4px;

        .products{
            display: flex;
            flex-direction: column;

            &.grid{
                flex-direction: row;
                flex-wrap: wrap;
                .product{
                    flex-basis: 25%;
                }
            }
        }


    }


</style>
