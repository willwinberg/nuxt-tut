<template>
  <div>
    <h1>{{ event.title }}</h1>
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
        event: data
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
