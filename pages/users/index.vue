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
  asyncData({$axios, error}) {
    return $axios.$get('https://jsonplaceholder.typicode.com/users')
      .then(users => {
        return {
          users
        }
      })
      .catch(err => {
        error(err)
      })
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
