<template>
  <header>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">Nuxt.js</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <nuxt-link exact class="nav-link" active-class="active" to="/">Home</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link no-prefetch class="nav-link" active-class="active" to="/users">Users</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" active-class="active" to="/about">About</nuxt-link>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {

}
</script>
