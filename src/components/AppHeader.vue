<script>
export default {
data() {
return {
    routes: [
        {
            label: 'Homepage',
            name:  'home'
        },
        {
            label: 'about',
            name: 'about'
        }
    ]
}
}
}
</script>

<template>
    <nav class="navbar bg-body-tertiary">
        <div class="container-fluid">
            <a class="navbar-brand">Navbar</a>
            <div>
                <ul>
                    <li v-for="route in routes">
                        <router-link :to="{ name: route.name}">
                            {{ route.label }}
                        </router-link>
                    </li>
                </ul>
            </div>
            <form class="d-flex" role="search">
            <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
            <button class="btn btn-outline-success" type="submit">Search</button>
            </form>
        </div>
    </nav>
</template>

<style scoped>

</style>