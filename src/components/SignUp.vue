<template>
<div class="container">
    <img class="logo" :src="require('../assets/kitchen-img.png')" />
    <h2>Sign Up</h2>
    <div class="register">
        <input type="text" v-model="name" placeholder="Enter Name" />
        <input type="email" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <button class="sign-btn" @click="signUp">sign up</button>
    </div>
</div>
</template>

<script>
import axios from 'axios';

export default {
    name: "SignUP",
    data() {
        return {
            name: '',
            email: '',
            password: ''
        }
    },
    methods: {
       async signUp() {
            console.warn("signUp", this.name, this.email, this.password)
            let result =await axios.post("http://localhost:3000/users",{
              email:this.email,
              name:this.name,
              password:this.password
            });
            console.warn(result);
            if(result.status==201){
              alert("Sign Up Done")
            }
            localStorage.setItem("user-info",JSON.stringify(result.da))
            
        }
    }

}
</script>

<style>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 10px;
}

.logo {
    margin-top: -60px;
    width: 300px;
}

.register {
    width: 300px;
    display: flex;
    flex-direction: column;
    gap: 15px;
}

input {
    padding: 10px;
    font-size: 16px;
    border: 1px solid gray !important;
    border-radius: 5px;
}

.sign-btn {
    background-color: gray;
    border: 1px solid gray;
    width: 300px;
    height: 40px;
}
</style>
