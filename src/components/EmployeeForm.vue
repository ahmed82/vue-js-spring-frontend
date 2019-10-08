<template>
    <form class="form">

        <label >Name: <input v-model="name" /></label>
        <label>Description: <input v-model="description" /></label>
        <button @click.prevent="onSubmit" >Submit</button>        
        <p>{{ name }}</p> 
        <p>{{ description }}</p> 
    </form>
    
</template>

<script>
import axios from 'axios';
// <label >Name: <input :value="name" @input="onNameUpdate" /></label> // : == bind prop ; @== onEven
// <label>Description: <input :value="description" @input="onDescriptionUpdate"/></label>
export default {
    data() {
        return {
            name: '',
            description: ''
        };
    },
    methods: {
        async onSubmit() {

            console.log(this.name, this.description)
            try {
                const results = await axios({ 
                    url: '/employees', 
                    data: {  name: this.name, descriptioin: this.description },
                    mode: 'no-cors', 
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    }
                });
            console.log(results.data);
            } catch (error) {
                console.log(error)
            }

        },
        // onNameUpdate(evt) {            
        //     this.name = evt.target.value;
        // },
        // onDescriptionUpdate(evt) {
        //     this.description = evt.target.value;
        // },        
    },
    // data: function() {},
    // data: () => {},
    
}
</script>
<style>
.form {
    display: flex;
    flex-direction: column;
}
</style>
