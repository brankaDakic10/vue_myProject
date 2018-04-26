<template>
  <div >
   {{message}}
 <button @click='notifyParent'> Notify Parent</button>
  </div>
</template>

<script>
export default {
  props:['message'],
  methods:{

   notifyParent(){
       this.$emit('notify-parent','Hello from child component')
   }


  }
}
</script>

<style>
</style>
