<template>
  <div>
    <h1>{{pageTitle}}</h1>

    <ul>
      <li
        v-for="user in users"
        :key="user"
      >
      <a href="#" @click.prevent="goTo(user)">User {{user}}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  asyncData() {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          users: [1, 2, 3, 4, 5]
        })
      }, 3000)
    })
  },
  data: () => ({
    pageTitle: 'This is users page'
  }),
  methods: {
    goTo(user) {
      this.$router.push('/users/' + user)
    }
  }
}
</script>
