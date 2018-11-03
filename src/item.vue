<template>
  <div class="">
      <h1>{{props.name}}</h1>
      <p>{{props.quantity}}</p>
      <div v-if="!props.incart">
          <h1>Need!</h1>
      </div>
      <div v-else>
          <h1>Don't Need!</h1>
      </div>
  </div>
</template>
<script>
//ToDo, pull state from store vs props
export default {
  props: [
    'props'
  ]
 

 }

</script>
<style scoped>

</style>