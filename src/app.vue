<template>
  <div class="full-width center-content">
    <h1 class="bold title">Shopping List</h1>
    <hr class="line">
      <div class="add-item full-width">
      <form class="form">
      <input class="textarea" type="text" v-model="newEntry" placeholder="Add Item">
      <input class="textarea number" type="number" v-model="newQuantity" placeholder="Add Amount">
      <i @click.prevent="getFormValues()" class="fas fa-plus"></i>
      </form>
      </div>
      <div class="item" v-for="(item,index) in items" :key="index">
        <i class="fas fa-plus-square" @click="item.quantity++"></i>
        <p class="quantity">{{item.quantity}}</p>
        <i class="fas fa-minus-square" @click="item.quantity--"></i>
        <!-- <item :props="item"></item> -->
        
        <h5 class="entry">{{item.name}}</h5>
        <div @click="item.incart=!item.incart" v-if="!item.incart">
          <i class="not fas fa-shopping-cart fa-2x"></i>
         </div>
        <div  @click="item.incart=!item.incart" v-else>
          <i class="contain fas fa-shopping-cart fa-2x"></i>
        </div>
        <i class="remove fas fa-times-circle" @click="removeitem(index)"></i>
      </div>
  </div>
</template>
<script>
  // import item from './item.vue';
  export default {
  // components: {
  //   item
  // },
  data(){
    return{
      items:[
        {name:"Lemons",quantity:4,incart:false},
        {name:"Chicken",quantity:1,incart:false},
        {name:"Cheese",quantity:2,incart:false},
        {name:"Milk",quantity:1,incart:false},
      ],
      newEntry:"",
      newQuantity:0,
    }
  },
  methods:{
    removeitem(index){
      this.items.splice(index,1);
    },
    getFormValues(){
      this.items.push({
        name:this.newEntry,
        quantity:this.newQuantity,
        incart:false
      })
    }
  },

}
</script>
<style scoped>

</style>