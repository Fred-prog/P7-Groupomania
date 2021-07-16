<template>
    <div class="login">
        <h1>Voici la page de login</h1>
        <LoginAuth />
    </div>
</template>

<script>

import LoginAuth from '../components/LoginAuth.vue'

export default {
    name: 'Login',
    components: {
        LoginAuth
    }
}
</script>