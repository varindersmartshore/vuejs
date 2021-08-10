<template>
  <div class="home">
      <img alt="Vue logo" src="../assets/logo.png">
      <Counter/>
      <DateTime/>
    <h1>This is a home page</h1>
  </div>
</template>
<script>
// @ is an alias to /src
import Counter from '@/components/Counter.vue'
import DateTime from '@/components/DateTime.vue'

export default {
  name: 'Home',
  components: {
    Counter,
    DateTime
  }
}

</script>