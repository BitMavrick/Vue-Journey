<template>
    <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">My Vue</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav">
                    <li v-for="(page, index) in pages" class="nav-item" :key="index">
                        <navbar-link :page="page" :isActive="activePage === index"
                            @click.prevent="navLinkClick(index)"></navbar-link>
                    </li>
                </ul>

            </div>
            <form class="d-flex">
                <button class="btn btn-primary" @click.prevent="changeTheme()">
                    Toggle Navbar
                </button>
            </form>
        </div>
    </nav>
</template>

<script>
import NavbarLink from './NavbarLink.vue';

export default {
    components: {
        NavbarLink
    },

    props: ['pages', 'activePage', 'navLinkClick'],

    data() {
        return {
            theme: 'light',
        };
    },
    methods: {
        changeTheme() {
            let theme = 'light';

            if (this.theme == 'light') {
                theme = 'dark';
            }

            this.theme = theme;
        }
    },
}

</script>