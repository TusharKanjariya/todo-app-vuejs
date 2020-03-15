<template>
<div id="Navigation">
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand" href="#">Navbar</a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item" v-for="nav in links" v-bind:key="nav.title">
          <router-link class="nav-link" v-bind:to="nav.path">
            {{nav.title}}
            <span class="sr-only">(current)</span>
          </router-link>
        </li>
      </ul>
    </div>
  </nav></div>
</template>

<script>
export default {
  name: "Navigation",
  data: function() {
    return {
      links: [
        { title: "Home", path: "/" },
        { title: "About", path: "/about" }
      ]
    };
  }
};
</script>