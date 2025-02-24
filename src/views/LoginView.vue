<template>
    <div>
        {{ usuario }}
        <h1>Login</h1>
        <label for="e">Ingresar correo:</label>
        <input type="email" v-model="usuario.email">
        <br>
        <label>Ingrese contraseña </label>
        <input type="password" v-model="usuario.password">
        <br>
        <input type="button" value="Ingresar" v-on:click="funIngresar()">
    </div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';

    //variables
    //const correo = ref("micorreo@mail.com");
    //const clave = ref("mi password");
    const usuario = ref({email:"",password:""})


    //metodos
    function funIngresar(){
        //axios.post("http://127.0.0.1:8000/api/v1/auth/login", {email: correo.value , password: clave.value}).then(
          axios.post("http://127.0.0.1:8000/api/v1/auth/login", usuario.value).then(
            (res)=>{
                console.log(res)
            }
        )
    }
</script>

