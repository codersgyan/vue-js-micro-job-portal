<template>
    <div class="box mt-4 mb-4">
        <h1 class="title is-5">{{ vacancy.title }}</h1>
        <span>{{ vacancy.company }}</span>
        <p>{{ vacancy.city }}</p>
        <div class="block"></div>
        <p>{{ vacancy.description }}</p>
        <div class="is-flex is-justify-content-space-between">
            <button @click="handleApply(vacancy)" class="button is-primary mt-4">Apply</button>
            <button v-if="isAdmin" @click="handleDelete(vacancy)" class="button is-danger mt-4">Delete</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Vacancy',
        props: {
            vacancy: {
                type: Object,
                required: true
            },
            isAdmin: {
                type: Boolean,
                required: true
            }
        },
        methods: {
            handleDelete(vacancy) {
                this.$emit('delete', vacancy.id);
            },
            handleApply(vacancy) {
                window.alert(`Applied successfully for ${vacancy.title}`);
            }
        }
    }
</script>

<style scoped>

</style>