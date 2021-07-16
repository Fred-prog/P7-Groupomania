<template>
    <div id="Form" class="my-5 align-items-center">
        <b-container class="py-5 border bg-secondary">
            <b-row align-h="center">
                <b-col sm="3" class="border bg-light">
                     <label for="input-horizontal">Adresse email</label>
                </b-col>
                <b-col sm="3">
                    <b-input-group prepend="@" class="mb-2 mr-sm-2 mb-sm-0">
                    <b-form-input id="input-horizontal" v-model="form.mail" ></b-form-input>
                    </b-input-group>
                </b-col>
            </b-row>
            <b-row class="py-4" align-h="center">
                <b-col sm="3" class="border bg-light">
                     <label for="input-horizontal">Mot de passe</label>
                </b-col>
                <b-col sm="3">
                    <b-form-input id="input-horizontal" class="ml-2" type="password" v-model="form.password" ></b-form-input>
                </b-col>
            </b-row>
            <b-row >
                <b-col cols="10">
                </b-col>
                <b-col cols="2">
                <b-button variant="primary" @click="sendForm">Connexion</b-button>
                </b-col>

            </b-row>
        </b-container>
    </div>
</template>

<script>
import axios from "axios"

    export default {
       name: 'LoginAuth',

       data() {
           return{
               form: {
                   mail: '',
                   password: ''
               }
           }
       },

       methods: {
           test() {
               alert(JSON.stringify(this.form))
           },
            sendForm() {
                axios.post("http://localhost:3000/api/auth/login", {
                    email: this.form.mail,
                    password: this.form.password
                } ).then((response) => {
                    console.log(response.data.token);
                    const resRequest = response;
                    // const orderId = resRequest.data.id;
                    console.log(resRequest.data.id);
                    // const orderTk = resRequest.data.token;
                    localStorage.setItem('user', JSON.stringify(response.data));
                    window.location = "http://localhost:8080/Wall";
                    }, (error) => {
                    console.log(error);
                    });
            }
       },
    }
</script>

<style lang="scss" scoped>
    
</style>