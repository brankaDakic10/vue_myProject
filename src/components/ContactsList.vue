<template>
  <div >
   
 <form @submit.prevent='addContact'>
      <label>First name</label>
      <input v-model='newContact.firstName' type='text' placeholder='First name'>
      <label>Last name</label>
      <input v-model='newContact.lastName'type='text' placeholder='Last name'>
      <label>Email</label>
      <input v-model='newContact.email' type='email' placeholder='Email'>
      <button type='submit'>Add contact</button>
  </form>


 <table>
  <thead>
    <th>Firstname</th>
    <th>Lastname</th> 
    <th>Email</th>
    <th>&nbsp</th>
  </thead>
  <tbody>
  <tr v-for="(contact, key) in contacts" :key="key">

    <td>{{contact.firstName}}</td>
    <td>{{contact.lastName}}</td>
   <td>{{contact.email}}</td>
    <td> 
    <button @click="removeContact(contact)"> Remove </button> 
    </td>
    </tr>
   </tbody>
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
   ],

   newContact:{
       firstName:'',
       lastName:'',
       email:''
         
      }
    }
    
  },

  methods:{
    addContact(){
       this.contacts.push(this.newContact)
       this.newContact={}

    },
     removeContact(contact){

    this.contacts.splice(this.contacts.indexOf(contact),1)
  }
}
}
</script>


</style>
