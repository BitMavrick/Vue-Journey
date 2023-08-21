<template>
    <div class="container">

        <h1 class="emphasize">{{ page.pageTitle }}</h1>
        <p>{{ page.content }}</p>

    </div>
</template>

<script>

export default {
    props: {
        page: {
            type: Object,
            default(rawProps) {
                return {
                    pageTitle: '',
                    content: '',
                }
            }
        }
    },
}

</script> 

<style scoped>
.emphasize {
    color: blue;
}
</style>