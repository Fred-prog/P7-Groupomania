<template>
    <div class="my-3">
        <b-container class="border px-3 py-3 rounded">
            <b-row>
                <b-col cols="1">
                    <p>User</p>
                </b-col>
                <b-col cols="6">
                <b-form-textarea 
                id="textarea"
                placeholder="entrer votre message"
                rows="1"
                max-rows="1"
                class="rounded-pill"
                v-model="form.content"></b-form-textarea>

                </b-col>
            </b-row>
            <b-row class="py-2">
                <b-col>
                <p>Ajouter photo</p>
                </b-col>
                <b-col>
                    <button v-on:click="test">image send</button>
                </b-col>
            </b-row>
            <b-row>
                <b-col></b-col>
                <b-col>
                <!-- <b-bouton variant="outline-success">ENVOYER</b-bouton> -->
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
import axios from 'axios'
    export default {
        name: 'WallWrite',

        data() {
            return {
                form: {
                   content: ''
                }
            }
        },

        methods: {

                test () {
                    alert(JSON.stringify(this.form.post))
                },

            submit () {
                axios.post("http://localhost:3000/api/contents", {
                    content: this.form.content
                })
                
                // manque verification auth
            }
        }

    }
</script>

<style lang="scss" scoped>

</style>