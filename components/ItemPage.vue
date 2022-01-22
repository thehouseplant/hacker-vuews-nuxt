<template>
  <span>
    <span>
      <a class="underline" :href="url" target="_blank">{{ title }}</a> ({{ domain }})
    </span>
    <p>
      <small>
        {{ points }} by {{ user }} {{ timeAgo }} | {{ commentsCount }} comments
      </small>
    </p>
  </span>
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
