<template>
    <div class="overflow-auto border bg-dark text-white" style="max-height: 750px">
        <b-container>
            <WallWrite />
        </b-container>
        <b-container class="py-2">
            <b-card>
                <p class="bg-secondary">
                {{ infos }}
                </p>
                <p>
                    {{  }}
                </p>
            </b-card>
            <b-card-group class="d-flex flex-column border border-info rounded py-3 px-3 bg-dark text-white" v-for='info in infos' v-bind:key='info.index'>
                <b-card-text class="d-flex">
                    <p> @ {{ info.post.user.username}} </p> || 
                    <p> {{ }} </p>
                </b-card-text>
                <b-card img src="" alt="">
                    image
                </b-card>
                <b-card class="bg-dark">
                    <p>
                        {{ info.post.content }}
                    </p>
                </b-card>
                <b-media>
                </b-media>
                <b-card-text> 
                    {{  }}
                    <p> {{  }} </p>
                </b-card-text>
                <b-card>
                    <b-row>
                        <b-col>
                        likes dislikes
                        </b-col>
                        <b-col>
                        link commentaire
                        </b-col>  
                    </b-row>
                    <b-card v-for="test in info.tests" v-bind:key="test">
                    <b-row class="bg-secondary">
                        
                        {{ info.test }}


                        
                    </b-row>
                    </b-card>
                </b-card>
                <!-- <b-card class="d-flex justify-content-end">
                <b-bouton id="modify">MODIFIER</b-bouton>
                <b-bouton id="delete">SUPRIMER</b-bouton>
                </b-card> -->
            </b-card-group>
        </b-container>
    </div>
</template>

<script>
import axios from 'axios'
import WallWrite from "../components/WallWrite.vue";
export default {
    name: 'WallChat',
    components: {
        WallWrite,
    },

    data() {
        return {
            infos: null,
            comms: null,
        }
    },

    // methods: {
    //     authHeader() {
    //         let user = JSON.parse(localStorage.getItem('user'));
    //         let test = console.log("il y a erreur");

    //         if (user && user.token) {
    //             return { Authorization: 'Bearer ' + user.token}
    //         } else {
    //             return {test};
    //         }
    //     }

    // },

mounted() {
        
        axios
            .get("http://localhost:3000/api/contents/")
            .then(response => {
                console.log(response.data);
                let data = [];
                data = response.data;
                this.infos = data
                data.forEach(function (post, index) {
                    let mot = {post}
                    data.splice(index, 1, mot)
                axios
                    .get("http://localhost:3000/api/contents/" + post.id + "/comments")
                    .then(response => {
                        let dataCom = response.data
                        let test = []
                        dataCom.forEach((coment) => {
                            if (post.id == coment.postId) {
                                console.log("voir comment: ", coment);
                                test.push(coment)
                                console.log("voir tableau test: ",test);
                                let testCom = true
                                let modifData = {post, test, testCom}
                                data.splice(index, 1, modifData)
                            }
                        })
                    }).catch(error => console.log(error))
                })   
        }).catch(error => console.log(error));
    }
}

</script>

<style lang="scss" scoped>

</style>