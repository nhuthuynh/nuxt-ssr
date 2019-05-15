<template>
  <div>
    <h1>{{ `${user.firstName} ${user.lastName}` }}</h1>
    <span>My id: {{ user.id }}</span>
  </div>
</template>
<script>
const getFirstAndLastNameOfUser = user => {
  if (!user) return ''
  return `${user.firstName} ${user.lastName}`
}
export default {
  data: function() {
    return {
      user: 'not user data yet'
    }
  },
  asyncData({ params }) {
    const userInfo = params.user.split('-')
    return {
      user: {
        firstName: userInfo[0] ? userInfo[0] : '',
        lastName: userInfo[1] ? userInfo[1] : '',
        id: userInfo[2] ? userInfo[2] : 0
      }
    }
  },
  head() {
    return {
      title: this.user,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: getFirstAndLastNameOfUser(this.user)
        }
      ]
    }
  }
}
</script>
