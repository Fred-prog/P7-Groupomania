<template>
    <div id="form">
        <b-container class="py-5 border bg-secondary">
            <b-row align-h="center">
                <b-col sm="3" class="border bg-light">
                    <label for="input-horizontal">Adresse email</label>
                </b-col>
                <b-col sm="3">
                    <b-input-group prepend="@" class="mb-2 mr-sm-2 mb-sm-0">
                    <b-form-input id="input-horizontal"></b-form-input>
                    </b-input-group>
                </b-col>
            </b-row>
            <b-row class="py-4" align-h="center">
                <b-col sm="3" class="border bg-light">
                    <label for="input-horizontal">Username</label>
                </b-col>
                <b-col sm="3">
                    <b-form-input id="input-horizontal" class="ml-2"></b-form-input>
                </b-col>
            </b-row>
            <b-row align-h="center">
                <b-col sm="3" class="border bg-light">
                    <label for="input-horizontal">Password</label>
                </b-col>
                <b-col sm="3">
                    <b-form-input id="input-horizontal" class="ml-2"></b-form-input>
                </b-col>
            </b-row>
            <b-row class="pt-4" align-h="center">
                <b-col cols="5">
                </b-col>
                <b-col cols="2">
                <b-button variant="primary">Inscription</b-button>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
    export default {
        name: "SignupAuth"
    }
</script>

<style lang="scss" scoped>

</style>