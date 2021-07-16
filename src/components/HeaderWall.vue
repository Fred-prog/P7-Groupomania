<template>
    <div>
        <div id="nav">
        <b-navbar toggleable="lg" type="dark" variant="info">
          <b-navbar-brand href="#" class="py-4 px-2">Groupomania</b-navbar-brand>
          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
          <b-collapse id="nav-collapse" is-nav>
          </b-collapse>
            <b-navbar-nav>
              <b-nav-item :to="'/'">Déconnexion</b-nav-item>
            </b-navbar-nav>
        </b-navbar>
      </div>
    </div>
</template>

<script>
    export default {
        name:'HeaderWall'
    }
</script>

<style lang="scss" scoped>

</style>