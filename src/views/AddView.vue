<template>
    <div className='formContainer'>
        <div>{{$route.params.id}}</div>
        <form className='add' @submit.prevent="handleSubmit">
        <h3>Add contact</h3>
        <label>Name</label>
        <input type="text" placeholder='Enter your name....' v-model="name" /><br>
        <label>Email</label>
        <input type="text" placeholder='Enter your email....' v-model="email" /><br>
        <label>Phone</label>
        <input type="text" placeholder='Enter your phone....' v-model="phone" /><br>
        <button class="btn">Submit</button>
        

        </form>
    </div>
</template>

<script>
    export default {
        name: 'AddView',
        emits: ['newUser', 'updateUser'],
        methods: {
            handleSubmit() {
                if (!this.isEditing) {
                    this.$router.push({name: 'home', params: { newUser: {
                        name: this.name,
                        email: this.email,
                        phone: this.phone
                        
                    } }})
                 }
            }
        },
        data () {
            return {
                name: '',
                email: '',
                phone: '',
                isEditing: false
            }
        }
    }

    
</script>

<style>

.formContainer {
    
    width: 1000px;
    max-width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #fff;
    padding: 20px 10%;
    
}

.formContainer form {
    width: 1100px;
    max-width: 100%;
    display: flex;
    flex-direction: column;
    padding: 20px 30px;
    border-radius: 5px;
    background-color: #dcdcdc;
    /* box-shadow: 0 0 15px; */
    gap: 0px;
}

.formContainer form input {
    height: 45px;
    border-radius: 5px;
    border: 1px solid #eaeeea;
    background-color: #ffffff;
    outline: none;
    padding: 10px;
    transition: .5s;

}

.formContainer form label {
    display: flex;
    align-items: flex-start;
    gap: 10px;
}

.formContainer  form button {
    background-color: black;
    color:  white;
    padding: 15px 30px;
    cursor: pointer;
    border: none;
    border-radius: 5px;
    transition: .5s;

}

.formContainer form input:focus {
    border-color: dodgerblue;
    caret-color: dodgerblue;
}


.formContainer  form button:hover {
    background-color:#1d1c1c;
    color: white;

}

</style>