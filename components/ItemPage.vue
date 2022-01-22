<template>
  <div>
    <h1>{{ item.title }}</h1>
    <p>
      {{ item.content }}
    </p>
    <p v-for="comment in item.comments" :key="comment.id">
      {{ comment.contents }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'ItemPage',
  props: {
    id: {
      type: Number,
      required: true
    }
  },
  data () {
    return {
      item: []
    }
  },
  beforeMount () {
    this.getItem()
  },
  methods: {
    async getItem () {
      const res = await fetch(`https://api.hackerwebapp.com/item/${this.$props.id}`)
      const data = await res.json()
      this.item = data
    }
  }
}
</script>
