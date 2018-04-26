<template>
  <div >
   {{ message }}
   <article>{{ reversedMessage }}</article>
   
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
},
computed:{

    reversedMessage(){
     return this.message.split('').reverse().join('')
    }
 }
}
</script>

<style>
</style>
