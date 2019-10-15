<template>
  <h1> User with id {{user.name}}</h1>
</template>

<script>
export default {
  validate({params}) {
    return /^\d+$/.test(params.id)
  },
  asyncData({params}) {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          user: {
            name: params.id
          }
        })
      }, 1500)
    })
  }
}
</script>
