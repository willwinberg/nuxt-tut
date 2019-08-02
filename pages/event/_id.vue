<template>
  <div>
    <h2>{{ event.title }}</h2>
  </div>
</template>
<script>
export default {
  head() {
    // this is a property used by vue-meta
    return {
      title: this.event.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: `Everything about event ${this.event.title}`
        }
      ]
    }
  },
  async asyncData({ $axios, error, params }) {
    try {
      const { data } = await $axios.get(
        `http://localhost:3000/events/${params.id}`
      )
      return {
        events: data
      }
    } catch (e) {
      error({
        statusCode: 503,
        message: `Unable to fetch event #${params.id}, please try again`
      })
    }
  }
}
</script>
