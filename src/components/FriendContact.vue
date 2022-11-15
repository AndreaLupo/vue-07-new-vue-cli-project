<template>
  <li>
    <h2>{{name}} {{ friendIsFavourite === '1' ? '(Favourite)': ''}}</h2>
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
            detailsAreVisible: false,
            friendIsFavourite: this.isFavourite
        };
    },
    props: ['name', 'phoneNumber', 'emailAddress', 'isFavourite'],
    methods: {
        toggleDetails() {
            this.detailsAreVisible = !this.detailsAreVisible;
        },
        toggleFavourite() {
            if (this.friendIsFavourite === '1' ) {
                this.friendIsFavourite ='0';
            }
            else if(this.friendIsFavourite === '0') {
                this.friendIsFavourite ='1';
            }
        }
    }
}
</script>

<style>

</style>