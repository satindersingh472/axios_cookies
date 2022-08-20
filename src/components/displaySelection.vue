<template>
    <div>
<img :src="images"/>
    </div>
</template>

<script>
    export default {
        methods: {
            display_image(random_url) {
                this.images = random_url;
            }
        },
        mounted () {
            this.$root.$on(`new_display`,this.display_image);
        },
        data() {
            return {
                images: undefined
            }
        },
    }
</script>

<style scoped>
img{
    height: 400px;
    width: 400px;
    border-radius: 50%;
    padding: 20px;
}
</style>