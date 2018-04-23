<template>
  <div >
    <table>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th> 
    <th>Email</th>
  </tr>
  <tr 
  v-for="(contact, key) in contacts" 
  :key="key" 
  v-if="contact.firstName ==='John'">

    <td>{{contact.firstName}}</td>
    <td>{{contact.lastName}}</td>
   <td>{{contact.email}}</td>
   
  </tr>
 
</table>
    
  </div>
</template>

<script>
export default {
  name: 'ContactsList',
  data(){
    return{

   contacts:[
     {firstName:'John',lastName:'Hohn',email:'john@yahoo.com'},
     {firstName:'Ann', lastName:'Jonson',email:'ana@yahoo.com'},
     {firstName:'Sam', lastName:'Smith', email:'sam@yahoo.com'}
   ]
    }
    
  }
}
</script>


</style>
