<template>
    <div>
        <h1>Posts</h1>
        <div class="box" v-for="post in posts" :key="post.id">
            <h1 class="title is-5">{{ post.title }}</h1>
            <p>{{ post.body }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                posts: []
            }
        },
        created() {
            fetch('https://jsonplaceholder.typicode.com/posts')
            .then(res => res.json())
            .then(data => {
                this.posts = data;
            })
        },
    }
</script>

<style scoped>

</style>