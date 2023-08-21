<template>
    <navbar :pages="pages" :active-page="activePage"></navbar>

    <page-viewer :page="pages[activePage]"></page-viewer>
</template>

<script>
import Navbar from './components/Navbar.vue';
import PageViewer from './components/PageViewer.vue';



export default {
    components: {
        Navbar,
        PageViewer
    },
    data() {
        return {
            activePage: 0,
            pages: [
                {
                    link: { text: 'Home', url: 'index.html' },
                    pageTitle: 'Home Page',
                    content: 'This is the home page content'
                },
                {
                    link: { text: 'About', url: 'about.html' },
                    pageTitle: 'About Page',
                    content: 'This is the about page content'
                },
                {
                    link: { text: 'Contact', url: 'contact.html' },
                    pageTitle: 'Contact Page',
                    content: 'This is the contact page content'
                },

            ]
        };
    },
}

</script>