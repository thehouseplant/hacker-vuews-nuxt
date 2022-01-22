<template>
  <div>
    <h1>{{ user.id }}</h1>
    <p>
      {{ user.about }}
    </p>
    <p v-if="user.karma">
      {{ user.karma }} points
    </p>
  </div>
</template>

<script>
export default {
  name: 'UserPage',
  props: {
    name: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      user: []
    }
  },
  beforeMount () {
    this.getUser()
  },
  methods: {
    async getUser () {
      const res = await fetch(`https://hacker-news.firebaseio.com/v0/user/${this.$props.id}.json?print=pretty`)
      const data = await res.json()
      this.user = data
    }
  }
}
</script>
