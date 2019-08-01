<template>
  <div>
    <h1>Events</h1>
  </div>
</template>
<script>
export default {
  head() { // this is a property used by vue-meta
    return {
      title: 'Event Listing - All the events ',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'literally all the events'
        }
      ]
    }
  }
}
</script>
