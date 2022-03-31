<template>
        <nav class="navbar navbar-dark bg-dark">
        <div class="container-fluid">

            <a href="/" class="navbar-brand my-logo">Marvel</a>

            <form class="d-flex">
                <input class="form-control me-2" type="search" placeholder="Поиск" aria-label="Search">
                <button class="btn btn-danger" type="submit">Всё</button>
            </form>
        </div>
    </nav>
</template>

<script>
    export default {
        name: "AppHeader",
        data() {
            return {
            }
        },
    }
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

.navbar>.container-fluid {
    flex-wrap: nowrap !important;
}

</style>
