<template>
  <div>
    <h1>{{pageTitle}}</h1>

    <ul>
      <li
        v-for="user in users"
        :key="user.id"
      >
      <a href="#" @click.prevent="goTo(user)">{{user.name}} ({{user.email}})</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({store, error}) {
    try {
      const users = await store.dispatch('users/fetchUsers')
      return {users}
    } catch (e) {
      error(e)
    }
  },
  data() {
    return {
      pageTitle: 'This is users page'
    }
  },
  methods: {
    goTo(user) {
      this.$router.push('/users/' + user.id)
    }
  }
}
</script>
