<template>
    <div id="app">
        <p>Current Date & Time: {{currentDateTime()}}</p>
    </div>
</template>
<script>

export default {
  methods: {
    currentDateTime() {
      const current = new Date();
      const date = current.getFullYear()+'-'+(current.getMonth()+1)+'-'+current.getDate();
      const time = current.getHours() + ":" + current.getMinutes() + ":" + current.getSeconds();
      const dateTime = date +' '+ time;

      return dateTime;
    }
  }
}

</script>