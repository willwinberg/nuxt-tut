<template>
  <div>
    <h2>Event #{{ id }}</h2>
  </div>
</template>
<script>
export default {
  head() {
    // this is a property used by vue-meta
    return {
      title: 'Event #' + this.id,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Everything about event #' + this.id
        }
      ]
    }
  },
  computed: {
    id() {
      return this.$route.params.id
    }
  }
}
</script>
