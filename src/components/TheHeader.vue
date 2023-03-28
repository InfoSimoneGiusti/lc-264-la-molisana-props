<script>
import MyLogo from './MyLogo.vue';

export default {
  name: "TheHeader",
  components: {
    MyLogo
  },
  data() {
    return {
      
    };
  },
  //props: ['cicciobello']
  props: {
    cicciobello: Array,
    paperino: Number
  }
};
</script>

<template>
  <header>
    <nav>
      <div class="brand">
        <!-- logo dell'azienda -->
        <MyLogo />
      </div>

      <ul class="navbar-links">
        <li v-for="(link, i) in cicciobello" :key="i">
          <a class="nav-link" :href="link.href">
            <i class="fas" :class="'fa-' + link.icon"></i>
            {{ link.text }}
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;
@use "../styles/partials/mixins";



header {
  background-color: $color-navbar-bg;
}

.brand {
  text-align: center;
}

.navbar-links {
  @include mixins.d-flex-center;
  list-style: none;

  .nav-link {
    padding: 1rem 1.5rem;
    color: black;
    text-decoration: none;
    transition: color 0.3s ease;
    display: inline-block;

    &:hover {
      color: $color-primary;
      text-decoration: underline;
    }
  }
}
</style>
