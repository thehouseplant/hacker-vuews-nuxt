<template>
  <span>
    <a class="underline" :href="url">{{ title }}</a> ({{ domain }})
    <br />
    <small>
      {{ points }} by {{ user }} {{ timeAgo }} | {{ commentsCount }} comments
    </small>
  </span>
</template>

<script>
export default {
  name: 'HnItem',
  props: {
    id: {
      type: Number,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    points: {
      type: Number,
      required: true
    },
    user: {
      type: String,
      required: true
    },
    timeAgo: {
      type: String,
      required: true
    },
    commentsCount: {
      type: Number,
      required: false,
      default: 0
    },
    domain: {
      type: String,
      required: true
    },
    url: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      data: []
    }
  },
  beforeMount () {
    // this.getPost()
  },
  methods: {
    async getPost () {
      const res = await fetch(`https://api.hackerwebapp.com/news/${this.$props.id}`)
      const data = await res.json()
      this.data = data
    }
  }
}
</script>
