<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-info mb-2">
    <div class="container">
      <a class="navbar-brand">Portal de noticias</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNavDropdown"
        aria-controls="navbarNavDropdown"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <router-link class="nav-link" to="/">
              Inicio
              <span class="sr-only">(current)</span>
            </router-link>
          </li>
          <li class="nav-item dropdown">
            <a
              class="nav-link dropdown-toggle"
              id="navbarDropdownMenuLink"
              data-toggle="dropdown"
              aria-haspopup="true"
              aria-expanded="false"
            >Categorías</a>
            <div class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
              <router-link
                class="dropdown-item"
                v-for="category in this.categoriesData"
                :key="category.id"
                :to="{ name: 'Category', params: { id: category.id } }"
              >{{ category.name }}</router-link>
            </div>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/contact">Contacto</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  props: {
    categoriesData: {
      type: Array
    }
  }
};
</script>