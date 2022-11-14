<template>
  <ul>
    <li v-for="friend of friends" :key="friend.id">
        <h2>{{friend.name}}</h2>
        <button @click="toggleDetails">Show Details</button>
        <ul v-if="detailsAreVisible">
        <li><strong>Phone:</strong> {{friend.phone}}</li>
        <li><strong>Email:</strong> {{friend.email}}</li>
        </ul>
    </li>
  </ul>
</template>

<script>
/**
 * Default export for this file when importing in ES-2015 sintax.
 */
export default {
    data () {
        return {
            friends: [
            { 
                    id: 'manuel',
                    name: 'Manuel Lorenz',
                    phone: '0123 3532 123',
                    email: 'manuel@localhost.com'
                },
                { 
                    id: 'julie',
                    name: 'Julie Jonez',
                    phone: '0123 3532 124',
                    email: 'julie@localhost.com'
                }
            ]
        };
    }
}
</script>

<style>

</style>