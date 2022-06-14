<template>
    <div>
        <h1>Users</h1>
        <nuxt-link to='/users/5'>Go to user number 5</nuxt-link>

        <ul>
            <li
                v-for="user in users"
                :key="user.id"
            >
                <nuxt-link :to="`users/${user.id}`">
                    {{ user.name }}
                </nuxt-link>
            </li>
        </ul>

    </div>
</template>

<script>
/*import { mapGetters } from 'vuex'

export default {
    computed: {
        ...mapGetters({
            users: 'user/getUsers'
        })
    },

    middleware: 'checkAuth'
}*/

export default {
    data() {
        return {
            users: []
        }
    },

    async created () {
        const response = await fetch('https://jsonplaceholder.typicode.com/users')
        this.users = await response.json()
    }
}

</script>