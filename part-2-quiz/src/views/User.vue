<template>
  <div>
    <h1>Welcome {{ $route.params.name }}</h1>
    <p> {{ test }} </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      test: 'Test'
    }
  }
}
</script>
