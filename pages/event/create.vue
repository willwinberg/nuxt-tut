<template>
  <div>
    <h1>Create an Events</h1>
  </div>
</template>
<script>
export default {
  head() {
    // this is a property used by vue-meta
    return {
      title: 'Create a new event',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'literally just create a new event'
        }
      ]
    }
  }
}
</script>
