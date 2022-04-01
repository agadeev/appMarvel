<template>
  <nav class="navbar navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand my-logo" href="#">Marvel</a>
      <form class="d-flex">

        <input
          class="form-control me-2"
          type="search"
          placeholder="Поиск..."
          aria-label="Search"
          v-model.trim="search"
          @keypress.enter.prevent
          @input="changeSearch(search)"
        />

        <button
          class="btn btn-danger"
          type="reset"
          @click="
            () => {
              search = '';
              changeSearch(search);
            }
          "
        >Все
        </button>
        
      </form>
    </div>
  </nav>
</template>

<script>
export default {
  name: "AppHeader",
  props: ["changeSearch"],
  data() {
    return {
      search: "",
    };
  },
};
</script>

<style scoped>
.my-logo {
  transform: scaleX(0.6);
  font-size: 1.75rem;
  letter-spacing: -0.1rem;
  line-height: 1.3;
  text-transform: uppercase;
  font-weight: 800;
  background: #dc3545;
  padding: 0 5px;
}

.navbar > .container-fluid {
  flex-wrap: nowrap !important;
}
</style>