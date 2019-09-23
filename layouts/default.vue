<template>
  <div>
    <nav
      class="navbar header has-shadow is-primary"
      role="navigation"
      aria-label="main navigation"
    >
      <div class="navbar-brand">
        <a class="navbar-item" href="/">Super Películas</a>

        <div class="navbar-burger" @click="isActive = !isActive">
          <span />
          <span />
          <span />
        </div>
      </div>

      <!-- Contenido del menú, al nivel del navbar-brand-->
      <div class="navbar-menu" :class="{active:isActive}">
        <div class="navbar-end">
          <div class="navbar-item">
            <div class="buttons">
              <a class="button">
                <strong>Registro</strong>
              </a>
              <a class="button is-light">
                Acceder
              </a>
            </div>
          </div>
        </div>
      </div>


    </nav>

    <section class="main-content columns">
      <aside class="column is-2 section">
        <p class="menu-label is-hidden-touch">
          General
        </p>
        <ul class="menu-list">
          <li
            v-for="(item, key) of items"
            :key="key"
          >
            <nuxt-link
              :to="item.to"
              exact-active-class="is-active"
            >
              <b-icon :icon="item.icon" /> {{ item.title }}
            </nuxt-link>
          </li>
        </ul>
      </aside>

      <div class="container column is-10">
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isActive: true,
      items: [
        {
          title: 'peliculas',
          icon: 'home',
          to: { name: 'index' }
        },
        {
          title: 'Favoritas',
          icon: 'lightbulb',
          to: { name: 'favoritas' }
        }
      ]
    }
  }
}
</script>

<style>
.active{
  display: block !important;
}
</style>