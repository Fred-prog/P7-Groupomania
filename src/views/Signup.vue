<template>
    <div class="signup">
    <h1>Voici la page d'inscription</h1>
    <SignupAuth/>
    </div>
</template>


<script>

import SignupAuth from '../components/SignupAuth.vue'

export default {
    name: 'Signup',
    components: {
        SignupAuth
    },
}
</script>