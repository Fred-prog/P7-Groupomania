<template>
    <header class="fluid">  
      <div id="nav">
        <b-navbar toggleable="lg" type="dark" variant="info">
          <b-navbar-brand href="#" class="py-4 px-2">Groupomania</b-navbar-brand>
          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
          <b-collapse id="nav-collapse" is-nav>
          </b-collapse>
            <b-navbar-nav v-if="['Login', 'Signup'].indexOf($route.name) > -1">
              <b-nav-item :to="'/'">LOGIN</b-nav-item>
              <b-nav-item :to="'/Signup'">SIGNUP</b-nav-item>
            </b-navbar-nav>
            <b-navbar-nav v-else>
              <b-nav-item :to="'/'">Déconnexion</b-nav-item>
            </b-navbar-nav>
        </b-navbar>
      </div>
    </header>
</template>

<script>
    export default {
        name:'Header',
    }
</script>

<style lang="scss" scoped>

</style>