<template>
  <li>
    <h2>{{name}}</h2>
    <button @click="toggleDetails">{{detailsAreVisible ? 'Hide': 'Show'}} Details</button>
    <ul v-if="detailsAreVisible">
    <li><strong>Phone:</strong> {{phoneNumber}}</li>
    <li><strong>Email:</strong> {{emailAddress}}</li>
    </ul>
  </li>
</template>

<script>
export default {
    data() {
        return {
            detailsAreVisible: false
        };
    },
    props: ['name', 'phoneNumber', 'emailAddress'],
    methods: {
        toggleDetails() {
            this.detailsAreVisible = !this.detailsAreVisible;
        }
    }
}
</script>

<style>

</style>