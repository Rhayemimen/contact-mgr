<template>
    <form class="row g-3" @submit.prevent="submitForm">
        <div class="col-md-6">
            <label for="inputEmail4" class="form-label">Name</label>
            <input type="text" class="form-control" id="inputEmail4" v-model="newContact.name">
        </div>
        <div class="col-md-6">
            <label for="inputPassword4" class="form-label">Email</label>
            <input type="email" class="form-control" id="inputPassword4" v-model="newContact.email">
        </div>
        <div class="col-12">
            <label for="inputAddress" class="form-label">Phone</label>
            <input type="text" class="form-control" id="inputAddress" v-model="newContact.phone">
        </div>
        <div class="col-6">
            <label for="inputAddress2" class="form-label">Street</label>
            <input type="text" class="form-control" id="inputAddress2" v-model="newContact.address.street">
        </div>
        <div class="col-md-6">
            <label for="inputCity" class="form-label">City</label>
            <input type="text" class="form-control" id="inputCity" v-model="newContact.address.city">
        </div>
        <div class="col-12">
            <button class="btn btn-primary">Valider</button>
        </div>
</form>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
    name:"Add",
    
    data() {
        return{
           newContact: {
               id: "",
               name: "",
               email: "",
               phone: "",
               address: {
                    street: "",
                    city: "",
                }
            }
        }
    },
    methods:{
        submitForm(){
            this.newContact.id = uuidv4()
            this.$emit('add-contact', this.newContact)
        }
    }
}

</script>

<style>

</style>