<template>
  <li>
    <h2>{{name}} {{ isFavourite ? '(Favourite)': ''}}</h2>
    <button @click="toggleFavourite"> Toggle favourite</button>
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
    // props: ['name', 'phoneNumber', 'emailAddress', 'isFavourite'],
    props: {
        id: {
            type: String,
            required: true
        },
        name: {
            type: String,
            required: true
        },
        phoneNumber: {
            type: String,
            required: true
        },
        emailAddress: {
            type: String,
            required: true
        },
        isFavourite: {
            type: Boolean,
            default: false
        },
    },
    methods: {
        toggleDetails() {
            this.detailsAreVisible = !this.detailsAreVisible;
        },
        toggleFavourite() {
            // this.friendIsFavourite = !this.friendIsFavourite;
            this.$emit('toggle-favourite', this.id);
        }
    }
}
</script>

<style>

</style>