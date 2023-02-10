<template>
  <nav
    class="navbar navbar-expand-lg"
    :class="{
      'navbar-success bg-success': !useDarkNav,
      'navbar-dark bg-dark': useDarkNav,
    }"
  >
    <a class="navbar-brand mx-4" href="">Navbar</a>

    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav" v-for="(page, index) in pages" :key="index">
        <a
          class="nav-item nav-link"
          :class="{ active: activePage == index }"
          :href="page.link.url"
          :title="`This link goes to ${page.link.text} page`"
          @click.prevent="navLinkClick(page, index)"
          >{{ page.link.text }}</a
        >
      </div>
    </div>
    <form class="d-flex">
      <button class="btn btn-primary" @click.prevent="useDarkNav = !useDarkNav">
        Change Nav color
      </button>
    </form>
  </nav>
</template>
<script>
export default {
  props: ["pages", "activePage", "NavLinkClick"],
  data() {
    return {
      useDarkNav: true,
    };
  },
  methods: {
    navLinkClick(page, index) {
      window.history.pushState({}, "", page.link.url);

      this.$emit("change-active-page", index);
    },
  },
};
</script>
