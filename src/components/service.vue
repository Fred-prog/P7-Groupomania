<template>
    <div>

    </div>
</template>

<script>
import axios from 'axios';
    export default {
        name: 'service',

        methods: {
            authHeader() {
                let user = JSON.parse(localStorage.getItem('user'));
                let test = console.log("il y a erreur");

                if (user && user.token) {
                    return { Authorization: 'Bearer ' + user.token}
                } else {
                    return {test};
                }
            }

        }

        
    }
</script>

<style lang="scss" scoped>

</style>